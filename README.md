# TinyGoはGo言語でマイコン・IoT機器・家電などを制御などで注目されている
マイコンとはゲームセンターのビデオゲームのような機器に、C言語やGo言語やPythonなどでプログラミングしたものを、チップに埋め込み動作させるマイクロコントローラーのことです。  

プログラミング言語の中でGo言語は、早く・新しく（改善され）・静的型付け言語（なので正確）・検索大手でAndoridの開発元のGoogleが開発元なので注目されているのかもしれません。

## TinyGoのインストール方法

**TinyGo**は、Go言語で記述されたマイコン向けのコンパイラです。様々なマイコンボードに対応しており、Go言語の文法で手軽にマイコンプログラミングを行うことができます。

### インストール手順

TinyGoのインストール方法は、ご使用のOSによって異なります。ここでは、一般的な手順を解説します。

#### 1\. **ツールチェーンのインストール**

TinyGoは、Goのツールチェーンを必要とします。まだインストールされていない場合は、Goの公式サイトからインストールしてください。

  * Goの公式サイト：[https://go.dev/doc/install](https://www.google.com/url?sa=E&source=gmail&q=https://go.dev/doc/install)

#### 2\. **TinyGoのインストール**

Goのツールチェーンがインストールされていることを確認後、以下のコマンドを実行してTinyGoをインストールします。

```bash
go install tinygo.org/x/tinygo/cmd/tinygo@latest
```

このコマンドを実行すると、`$GOPATH/bin`ディレクトリに`tinygo`コマンドがインストールされます。

#### 3\. **インストール確認**

インストールが成功していれば、以下のコマンドを実行して、TinyGoのバージョンを確認できます。

```bash
tinygo version
```

### 環境変数の設定 (必要に応じて)

  * **$GOPATH/bin**を`PATH`環境変数に追加する
    これにより、任意のディレクトリから`tinygo`コマンドを実行できるようになります。

### その他

  * **特定のバージョンをインストールする場合:**
    ```bash
    go install tinygo.org/x/tinygo/cmd/tinygo@v0.21.0
    ```
    のように、バージョンを指定してインストールできます。
  * **詳細なインストール手順:**
    TinyGoの公式ドキュメントに、より詳細なインストール手順が記載されています。
    [https://tinygo.org/getting-started/install/](https://www.google.com/url?sa=E&source=gmail&q=https://tinygo.org/getting-started/install/)

### TinyGoの利用例

```go
package main

import "machine"

func main() {
        led := machine.LED
        led.Configure(machine.PinConfig{Mode: machine.PinOutput})

        for {
                led.High()
                time.Sleep(time.Second)
                led.Low()
                time.Sleep(time.Second)
        }
}
```

このコードは、Arduino Unoなどのボードに搭載されているLEDを1秒間隔で点滅させるプログラムです。

### まとめ

TinyGoのインストールは、Goのツールチェーンをインストールし、`go install`コマンドを実行するだけで簡単に行えます。TinyGoを利用することで、Go言語の知識を活かして様々なマイコンボードを制御することができます。

**ご注意:**

  * インストール手順やコマンドは、TinyGoのバージョンやOSによって異なる場合があります。
  * マイコンボードの種類によって、必要なドライバや設定が異なる場合があります。

**より詳しい情報については、TinyGoの公式ドキュメントをご参照ください。**

**よくある他の疑問**

  * 特定のマイコンボードでTinyGoを使いたい
  * TinyGoでI/Oを制御する方法を知りたい
  * TinyGoの開発環境について知りたい
    など、ご質問いただければ、お答えします。
