```Typescript
export const databaseProviders = [
	{
		provide: MysqlDatasourceKey,
		inject: [ConfigService, MysqlConfigService],
		useFactory: async (
			configService: ConfigService,
			databaseConfigService: MysqlConfigService,
		) => {
			const dataSource = new DataSource(
				databaseConfigService.getTypeormConfig(),
			);
			return dataSource.initialize();
		},
	},
];
```

> 위와 같은 상황에서 useFactory에 인자에는 무조건 **`inject`배열의 순서**대로 인스턴스가 들어온다

- 참고
	- `MySqlConfigService` 는  `ConfigService`에 의존성이 있다.
	- 위와 같은 경우에서 `ConfigService`는 `AppModule`에서 `global: true`로 사용 중 이었기 때문에 `inject`할 필요는 없었다.
