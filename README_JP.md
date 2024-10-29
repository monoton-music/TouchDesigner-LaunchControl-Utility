# TD-LaunchControl-Utility
日本語版ドキュメントは英語版から情報を抜粋していたり、更新が遅れていたりすることがあります。
参考までにご覧ください。  
より正確な情報については[README.md](README.md)をご覧ください。

Novation Launch Control XLをTouchDesignerと統合し、ノブやスライダーのマッピングを簡単に行うためのユーティリティです。

## Compatibility
このツールはNovation Launch Control XL MK2での動作が確認されています。他のモデルのLaunch Control XLでは動作しない可能性があります。toxファイルおよびサンプルプロジェクトファイルはTouchDesignerバージョン2023.11600で作成されました。

## 使用方法

詳細な使用方法や例については、プロジェクトに含まれている`example.toe`ファイルを開いて確認してください。

### Step 1: Launch Control XLをコンピュータに接続する
- Launch Control XLを`User Mode 1`に設定します。

### Step 2: TouchDesignerでMIDIデバイスマッパーを設定する
- TouchDesignerの`Dialogues`メニューから`MIDI Device Mapper`を選択します。
- 新しいマッピングを作成し、`Input Device`を`Launch Control XL`に設定します。

### Step 3: Masterコンポーネントを設定する
- TouchDesignerプロジェクト内でこのユーティリティを使用するパスのディレクトリ階層の同じレベルまたは上位レベルに`launchcontrol_master.tox`を配置します。例えば、`project1`に配置します。

### Step 4: Master COMPを構成する
- `launchcontrol_master.tox`内で、Launch Control XLの`Device ID`と`MIDI Channel`を設定します。
- ユーティリティが正しく動作しない場合は、`launchcontrol_master.tox`内の`Reset`ボタンを押します。

### Step 5: Selectorコンポーネントを設定する
- `launchcontrol_select.tox`を、ノブやスライダーの値を割り当てたい場所に配置します。

### Step 6: Selectorコンポーネントを構成する
- `launchcontrol_select.tox`内の`Custom`ページを開き、以下のパラメータを設定します：
    - **Master OP Name:** `Launch Control_master`と入力します。
    - **Depth Level:** 現在の`launchcontrol_select.tox`の位置から`launchcontrol_master.tox`がある階層までの階層数を設定します。例えば、`launchcontrol_master.tox`が2階層上にある場合、`Depth Level`を`2`に設定します。
    - **Control Group:** 目的のノブまたはスライダーのグループを選択します。
    - **Control Number:** 目的のノブまたはスライダーの番号を選択します。
    - **Output Mode:** 以下のモードから選択します：
        - **Unipolar:** `Unipolar Range`内で値を線形に出力します。
        - **Bipolar** (ノブのみ): ノブがセンタークリック位置に設定されている場合に`Bipolar Center`を出力し、`Bipolar Range`内で値を出力します。
        - **Exponential:** `Exponential Min-Max Ratio`の比率で、`Exponential Range`内で値を指数関数的に出力します。
    - **Output Lag:** 出力の遅延時間を設定します。
    - **Output Filter Width:** 出力に適用するフィルターの幅を設定します。

### Step 7: Selector COMPの値を使用する
- `launchcontrol_select.tox`の出力に接続するか、`launchcontrol_select.tox`から直接Export CHOPを使用して値を利用します。

## ライセンス
このプロジェクトはMITライセンスの下でライセンスされています。

## 商標
Launch ControlはFocusriteの登録商標です。本プロジェクトは、Focusriteと提携しておらず、Focusriteの承認を受けていません。

## About the Developer
### monoton  
music producer, DJ & VJ, (virtual) experience design, generative visual design  
[Linktree](https://linktr.ee/monoton)
