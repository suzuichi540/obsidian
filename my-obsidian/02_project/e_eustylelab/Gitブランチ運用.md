
Git ブランチの運用および命名に関するガイドラインです。

## 目次

[](https://github.com/eustylelab/readme/blob/master/docs/guidelines/git-branch-guideline.md#%E7%9B%AE%E6%AC%A1)

- [master ブランチについて](https://github.com/eustylelab/readme/blob/master/docs/guidelines/git-branch-guideline.md#master-branch)
- [develop ブランチ/release](https://github.com/eustylelab/readme/blob/master/docs/guidelines/git-branch-guideline.md#develop-branch-and-release-branch)
- [トピックブランチ（作業用ブランチ）について](https://github.com/eustylelab/readme/blob/master/docs/guidelines/git-branch-guideline.md#topic-branch)
    - [命名規則](https://github.com/eustylelab/readme/blob/master/docs/guidelines/git-branch-guideline.md#topic-branch-naming-standard)
- [プロジェクトブランチについて](https://github.com/eustylelab/readme/blob/master/docs/guidelines/git-branch-guideline.md#project-branch)
    - [命名規則](https://github.com/eustylelab/readme/blob/master/docs/guidelines/git-branch-guideline.md#project-branch-naming-standard)

## master ブランチについて

[](https://github.com/eustylelab/readme/blob/master/docs/guidelines/git-branch-guideline.md#master-%E3%83%96%E3%83%A9%E3%83%B3%E3%83%81%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6)

- 《必須》開発を複数人で行うようになった場合は必ずプルリクエストを作成するようにしてください。 開発を1人で担当している間は master に直接 commit/push しても構いません。

## develop ブランチ/release ブランチについて

[](https://github.com/eustylelab/readme/blob/master/docs/guidelines/git-branch-guideline.md#develop-%E3%83%96%E3%83%A9%E3%83%B3%E3%83%81release-%E3%83%96%E3%83%A9%E3%83%B3%E3%83%81%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6)

- 《参考》現時点では採用しません。

## トピックブランチ（作業用ブランチ）について

[](https://github.com/eustylelab/readme/blob/master/docs/guidelines/git-branch-guideline.md#%E3%83%88%E3%83%94%E3%83%83%E3%82%AF%E3%83%96%E3%83%A9%E3%83%B3%E3%83%81%E4%BD%9C%E6%A5%AD%E7%94%A8%E3%83%96%E3%83%A9%E3%83%B3%E3%83%81%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6)

- 《必須》トピックブランチは原則として master ブランチから作成してください。ただし、下記の場合はその限りではありません。
    - まだ master にマージされていない他のブランチの変更が前提となる場合。
    - [プロジェクトブランチ](https://github.com/eustylelab/readme/blob/master/docs/guidelines/git-branch-guideline.md#project-branch)から分岐し、プロジェクトブランチにマージする場合。

### 命名規則

[](https://github.com/eustylelab/readme/blob/master/docs/guidelines/git-branch-guideline.md#%E5%91%BD%E5%90%8D%E8%A6%8F%E5%89%87)

- 《必須》下記の通りとししてください。

```
（ブランチ種別）/（課題番号）_（ブランチの説明）
```

- 《必須》課題番号には Backlog の課題番号を小文字で用いてください。
- 《必須》ブランチの説明は kebab-case としてください。

ブランチ種別およびブランチ名の例は次の通りです。

|ブランチ種別|ブランチの目的|例|
|:--|:--|:--|
|feature|新機能追加・機能改善等|feature/dev-1234_add-awesome-feature|
|fix|不具合修正|fix/dev-1234_remove-unused-variables|
|misc|ドキュメント整備等、コードの変更を伴わない作業|misc/dev-1234_improve-readme|

#### 例

[](https://github.com/eustylelab/readme/blob/master/docs/guidelines/git-branch-guideline.md#%E4%BE%8B)

以下にいくつかの正しい例・間違った例を挙げます。

|o/x|ブランチ名|NG理由|
|:-:|:--|:--|
|o|feature/dev-1234_add-download-button||
|o|fix/dev-1234_remove-unused-variables||
|x|feature/dev-1234|ブランチの説明がない|
|x|feature/dev-1234_ADD-DOWNLOAD-BUTTON|ブランチの説明が大文字|
|x|feature/dev-1234_add_download_button|ブランチの説明が snake_case|
|x|feature/dev-1234-addDownloadButton|ブランチの説明が camelCase|
|x|feature/dev-1234-AddDownloadButton|ブランチの説明が PascalCase|
|x|feature/dev-1234-add-download-button|課題番号と説明の区切りがハイフン|
|x|feature/add-download-button|課題番号が抜けている|

## プロジェクトブランチについて

[](https://github.com/eustylelab/readme/blob/master/docs/guidelines/git-branch-guideline.md#%E3%83%97%E3%83%AD%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E3%83%96%E3%83%A9%E3%83%B3%E3%83%81%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6)

- 《必須》1回のプルリクエストで完了しないような大きな開発案件については、*_プロジェクトブランチ_- を作成してください。
- 《必須》プロジェクトブランチには直接 commit/push せず、必ずプルリクエストを作成するようにしてください。
- 《必須》プロジェクトブランチから分岐したトピックブランチは master ブランチへマージ/プルリクエストせずにプロジェクトブランチにマージ/プルリクエストをするようにしてください。
- 《必須》必要なトピックブランチをすべてマージしたら、master ブランチへのプルリクエストを作成してください。

### 命名規則

[](https://github.com/eustylelab/readme/blob/master/docs/guidelines/git-branch-guideline.md#%E5%91%BD%E5%90%8D%E8%A6%8F%E5%89%87-1)

- 《必須》下記の通りとしてください。

```
project/（課題番号）_（プロジェクトの説明）
```

- 《必須》課題番号には Backlog の課題番号を小文字で用いてください。
- 《必須》プロジェクトの説明は kebab-case としてください。

#### 例

[](https://github.com/eustylelab/readme/blob/master/docs/guidelines/git-branch-guideline.md#%E4%BE%8B-1)

以下にいくつかの正しい例・間違った例を挙げます。

|o/x|ブランチ名|NG理由|
|:-:|:--|:--|
|o|project/dev-1234_add-download-button||
|o|project/dev-1234_remove-unused-variables||
|x|project/dev-1234|プロジェクトの説明がない|
|x|project/dev-1234_ADD-DOWNLOAD-BUTTON|プロジェクトの説明が大文字|
|x|project/dev-1234_add_download_button|プロジェクトの説明が snake_case|
|x|project/dev-1234-addDownloadButton|プロジェクトの説明が camelCase|
|x|project/dev-1234-AddDownloadButton|プロジェクトの説明が PascalCase|
|x|project/dev-1234-add-download-button|課題番号と説明の区切りがハイフン|
|x|project/add-download-button|課題番号が抜けている|