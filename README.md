# AppiumTestReportBDDSample
[Appium](http://appium.io/)でWindowsアプリのUIテストを実行して、その結果を[ExtentReports](https://extentreports.com/)でHTML形式で出力してみました。
[BDD（ビヘイビア駆動開発）](https://ja.wikipedia.org/wiki/%E3%83%93%E3%83%98%E3%82%A4%E3%83%93%E3%82%A2%E9%A7%86%E5%8B%95%E9%96%8B%E7%99%BA)フレームワークの[SpecFlow](https://specflow.org/)（Rubyで開発されたBDDフレームワーク[Cucumber](https://en.wikipedia.org/wiki/Cucumber_(software))の.NET版です）でUIテストを記述しました。</br>
このリポジトリのHTMLはSpecFlowを用いて記述したUIテスト結果のレポートをExtentReportsで出力したものです。

- HTMLレポートの「メニューバーテスト（ヘルプ）」項目は下記のようにテストケースを記述しています（Given、When、Thenで始まるそれぞれの記述に対応するメソッドが別のファイルにあり、そこに引数を渡して実行しています）。
```
Feature: メニューバーテスト（ヘルプ）
    メニューバーのヘルプ項目の選択および表示テスト

Scenario Outline: HelpSelectTest
  Given メニューバーの<MenuItemName1>をクリック
  When メニューアイテムの<MenuItemName2>をクリック
  When ウィンドウのタイトルが<TitleName>と一致するかを確認
  Then ボタン<ButtonName>をクリック

  Examples:
    | MenuItemName1 | MenuItemName2                | TitleName        | ButtonName            |
    | "ヘルプ"      | "バージョン情報"             | "バージョン情報" | "VersionInfoOkButton" |
    | "ヘルプ"      | "使用許諾契約書"             | "使用許諾契約書" | "ContractDocOkButton" |
    | "ヘルプ"      | "ドキュメントフォルダを開く" | "エラー"         | "OkButton"            |

```

# 参考資料
- Appium:
http://appium.io/

- SpecFlow:
https://specflow.org/

- ExtentReports:
https://extentreports.com/

- ビヘイビア駆動開発:
https://ja.wikipedia.org/wiki/%E3%83%93%E3%83%98%E3%82%A4%E3%83%93%E3%82%A2%E9%A7%86%E5%8B%95%E9%96%8B%E7%99%BA

- 参考にした動画:
https://www.youtube.com/watch?v=tfq9FlkyaUM&list=PL6tu16kXT9Pp3wrsaYyNRnK1QkvVv6qdI
