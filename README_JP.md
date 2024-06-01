# TouchDesigner-LaunchControl-Utility
Novation LaunchControl XLをTouchDesignerと統合し、ノブやスライダーの簡単なマッピングを可能にするユーティリティです。

## 使用方法

1. LaunchControl XLをコンピュータに接続します。

2. LaunchControl XLを`User Mode 1`に設定します。

3. TouchDesignerで、`Dialogues`メニューから`MIDI Device Mapper`を選択します。

4. 新しいマッピングを作成し、`Input Device`を`LaunchControl XL`に設定します。

5. TouchDesignerプロジェクト内でこのユーティリティを使用するパスのディレクトリ階層の同じレベルまたは上位レベルに`launchcontrol_master.tox`を配置します。

    例えば、`project1`に配置します。

6. `launchcontrol_master.tox`で、LaunchControl XLの`Device ID`と`MIDI Channel`を設定します。

    ユーティリティが正常に動作しない場合は、`launchcontrol_master.tox`で`Reset`を押します。

7. `launchcontrol_select.tox`を、ノブやスライダーの値を割り当てたい場所に配置します。

8. `launchcontrol_select.tox`の`Custom`ページを開きます。

9. 以下のパラメータを設定します：

    - **Master OP Name**: `LaunchControl_master`と入力します。
    - **Depth Level**: 現在の`launchcontrol_select.tox`の位置から`launchcontrol_master.tox`がある階層までの階層数を設定します。例えば、`launchcontrol_master.tox`が2階層上にある場合、`Depth Level`を`2`に設定します。
    - **Control Group**: 目的のノブまたはスライダーのグループを選択します。
    - **Control Number**: 目的のノブまたはスライダーの番号を選択します。
    - **Output Mode**: 以下のモードから選択します：
        - **Unipolar**: `Unipolar Range`内で値を線形に出力します。
        - **Bipolar** (ノブのみ): ノブがセンタークリック位置に設定されている場合に`Bipolar Center`を出力し、`Bipolar Range`内で値を出力します。
        - **Exponential**: `Exponential Min-Max Ratio`の比率で、`Exponential Range`内で値を指数関数的に出力します。
    - **Output Lag**: 出力の遅延時間を設定します。
    - **Output Filter Width**: 出力に適用するフィルターの幅を設定します。

10. ノブやスライダーの値を次のいずれかの方法で使用します：

    - `launchcontrol_select.tox`の出力に接続する。
    - `launchcontrol_select.tox`のBase COMPから直接Export CHOPを使用する。

## ライセンス
MITライセンス

## 作者について
monoton  
music producer, DJ & VJ, (virtual) experience design, generative visual design  
[Linktree](https://linktr.ee/monoton)

### サポート
このプロジェクトが役に立った場合は、ぜひサポートをお願いします！

<a href="https://www.buymeacoffee.com/monoton" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-orange.png" alt="Buy Me A Coffee" height="41" width="174"></a>
