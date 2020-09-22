# sample-gradle-phase

## 実行結果
初期化フェーズ：外部プロパティ<br>
<br>
> Configure project :<br>
設定フェーズ：前：拡張プロパティ１：外部プロパティ<br>
設定フェーズ：configrations：外部プロパティ<br>
設定フェーズ：dependensies：外部プロパティ<br>
設定フェーズ：中：拡張プロパティ１：拡張プロパティ２：外部プロパティ<br>
設定フェーズ：タスク内：外部プロパティ<br>
設定フェーズ：後：拡張プロパティ１：拡張プロパティ２：外部プロパティ<br>
<br>
> Task :clean<br>
タスク実行フェーズ：doFirst：外部プロパティ<br>
タスク実行フェーズ：doLast：外部プロパティ<br>
