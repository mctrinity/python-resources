# Pandas Features in Python

## 1. Data Structures
- `pd.Series` – One-dimensional labeled array.
- `pd.DataFrame` – Two-dimensional labeled data structure.
- `pd.Index` – Immutable sequence used for indexing.

## 2. Creating DataFrames
- `pd.DataFrame(data)`
- `pd.read_csv(filepath)` – Read CSV file.
- `pd.read_excel(filepath)` – Read Excel file.
- `pd.read_json(filepath)` – Read JSON file.
- `pd.read_sql(query, connection)` – Read SQL query.
- `pd.read_html(url)` – Read HTML tables.
- `pd.read_parquet(filepath)` – Read Parquet file.
- `pd.read_pickle(filepath)` – Read Python pickle file.

## 3. Viewing & Inspecting Data
- `df.head(n)` – View first `n` rows.
- `df.tail(n)` – View last `n` rows.
- `df.info()` – Summary of DataFrame.
- `df.describe()` – Summary statistics.
- `df.shape` – Dimensions of DataFrame.
- `df.columns` – Column names.
- `df.index` – Index of DataFrame.
- `df.dtypes` – Data types of columns.
- `df.memory_usage()` – Memory usage of DataFrame.

## 4. Selection & Indexing
- `df['column']` – Select single column.
- `df[['col1', 'col2']]` – Select multiple columns.
- `df.loc[row_label, col_label]` – Label-based selection.
- `df.iloc[row_index, col_index]` – Index-based selection.
- `df.at[row_label, col_label]` – Access single value by label.
- `df.iat[row_index, col_index]` – Access single value by index.
- `df.query('condition')` – Query using expressions.

## 5. Filtering & Boolean Indexing
- `df[df['column'] > value]`
- `df[df['column'].isin([val1, val2])]`
- `df[df['column'].str.contains('string')]`
- `df[df.duplicated()]` – Find duplicates.
- `df[df.isnull()]` – Find missing values.

## 6. Sorting & Ordering
- `df.sort_values(by='column', ascending=True)`
- `df.sort_index(ascending=True)`

## 7. Aggregations & Statistics
- `df.count()`, `df.sum()`, `df.mean()`, `df.median()`
- `df.min()`, `df.max()`, `df.std()`, `df.var()`
- `df.corr()`, `df.cumsum()`

## 8. Handling Missing Data
- `df.isnull()`
- `df.notnull()`
- `df.dropna()`
- `df.fillna(value)`
- `df.interpolate()`

## 9. Grouping & Aggregation
- `df.groupby('column').agg(func)`
- `df.groupby('column').sum()`
- `df.groupby('column').mean()`
- `df.groupby(['col1', 'col2']).count()`
- `df.pivot_table(index='column', values='values', aggfunc='sum')`

## 10. Merging, Joining & Concatenation
- `pd.concat([df1, df2])`
- `df1.append(df2)`
- `df1.merge(df2, on='column', how='inner')`
- `df1.join(df2, on='column')`

## 11. Exporting Data
- `df.to_csv(filepath, index=False)`
- `df.to_excel(filepath)`
- `df.to_json(filepath)`
- `df.to_sql(table, connection)`
- `df.to_html(filepath)`
- `df.to_parquet(filepath)`
- `df.to_pickle(filepath)`
