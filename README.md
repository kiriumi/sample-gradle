# sample-gradle-phase
## 補足
* 外部拡張プロパティはどこからでも見れる（初期化フェーズでも）
* 設定フェーズはコーディング順（上から）動く
* doFirst, doLastは実際に動くタスクの前後に動く
* クロージャ内からだと、内部拡張プロパティは見れない？*

## Gradleのフェーズ
### 初期化フェーズ：プロジェクト構成を把握
* プロパティファイルの読込み
  * gradle.properties
* プロジェクト構成の把握
  * settings.gradle
	
### 設定フェーズ：各プロジェクト内のタスク構成・設定を把握し、タスクの動作を確定
* ルートプロジェクトのallprojects, subprojects, config
* 各プロジェクト内の設定プラグイン、依存関係、configrations、その他設定の読込み
  * allprojects, subprojects, config
  * plugins
  * dependensies
  * configrations
  * その他設定
* タスクを把握

### タスク実行フェーズ：指定されたタスクの実行
* タスクの実行

## 実行結果
初期化フェーズ：外部プロパティ<br>

> Configure project :<br>
設定フェーズ：前：拡張プロパティ１：外部プロパティ<br>
設定フェーズ：configrations：外部プロパティ<br>
設定フェーズ：dependensies：外部プロパティ<br>
設定フェーズ：中：拡張プロパティ１：拡張プロパティ２：外部プロパティ<br>
設定フェーズ：タスク内：外部プロパティ<br>
設定フェーズ：後：拡張プロパティ１：拡張プロパティ２：外部プロパティ<br>

> Task :clean<br>
タスク実行フェーズ：doFirst：外部プロパティ<br>
タスク実行フェーズ：doLast：外部プロパティ<br>
