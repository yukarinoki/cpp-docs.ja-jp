---
description: '詳細については、「方法: WRL を使用してイベントを処理する」を参照してください。'
title: '方法: WRL を使用してイベントを処理する'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1c77543f-7b0c-4a94-93bf-e3225885ed76
ms.openlocfilehash: b1be04c1356594e2dc2060d031f35d836ad277bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229185"
---
# <a name="how-to-handle-events-using-wrl"></a>方法: WRL を使用してイベントを処理する

このドキュメントでは、Windows ランタイム C++ テンプレートライブラリ (WRL) を使用して、Windows ランタイムオブジェクトのイベントをサブスクライブおよび処理する方法について説明します。

そのコンポーネントのインスタンスを作成してプロパティ値を取得する、より基本的な例については、「 [方法: Windows ランタイムコンポーネントをアクティブ化して使用](how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)する」を参照してください。

## <a name="subscribing-to-and-handling-events"></a>イベントのサブスクライブと処理

次の手順では `ABI::Windows::System::Threading::IDeviceWatcher` オブジェクトを開始し、イベント ハンドラーを使用して進行状況を監視します。 `IDeviceWatcher` インターフェイスを使用すると、デバイスを非同期的にまたはバックグラウンドで列挙でき、デバイスが追加、削除、または変更された場合に通知を受け取ることができます。 [コールバック](callback-function-wrl.md)関数は、バックグラウンド操作の結果を処理するイベントハンドラーを指定できるようにするため、この例の重要な部分です。 完全な例を次に示します。

> [!WARNING]
> 通常はユニバーサル Windows プラットフォームアプリで Windows ランタイム C++ テンプレートライブラリを使用しますが、この例ではコンソールアプリを使用して説明します。 などの関数 `wprintf_s` は、ユニバーサル Windows プラットフォームアプリからは使用できません。 ユニバーサル Windows プラットフォームアプリで使用できる型と関数の詳細については、「 [ユニバーサル Windows プラットフォームアプリでサポートされない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) 」および「 [UWP アプリの Win32 および COM](/uwp/win32-and-com/win32-and-com-for-uwp-apps)」を参照してください。

1. 必須の `#include` Windows ランタイム、Windows ランタイム C++ テンプレートライブラリ、または C++ 標準ライブラリのヘッダーを含めます。

   [!code-cpp[wrl-consume-event#2](../codesnippet/CPP/how-to-handle-events-using-wrl_1.cpp)]

   `Windows.Devices.Enumeration.h` デバイスを列挙するために必要な型を宣言します。

   コードを読みやすくするために、.cpp ファイルでは `using namespace` ディレクティブを使用することをお勧めします。

2. アプリ用のローカル変数を宣言します。 この例では、後でイベント サブスクリプションを解除できるようにするために、列挙されたデバイスと登録トークンの数を保持します。

   [!code-cpp[wrl-consume-event#7](../codesnippet/CPP/how-to-handle-events-using-wrl_2.cpp)]

3. Windows ランタイムを初期化します。

   [!code-cpp[wrl-consume-event#3](../codesnippet/CPP/how-to-handle-events-using-wrl_3.cpp)]

4. 列挙プロセスの完了をメインアプリに同期する [イベント](event-class-wrl.md) オブジェクトを作成します。

   [!code-cpp[wrl-consume-event#4](../codesnippet/CPP/how-to-handle-events-using-wrl_4.cpp)]

   > [!NOTE]
   > このイベントは、コンソール アプリケーションの一部としてデモのみを目的としています。 この例では、アプリケーションが終了する前に非同期操作が完了したことを確認するために、イベントを使用します。 ほとんどのアプリケーションでは、通常は非同期操作の完了を待機しません。

5. `IDeviceWatcher` インターフェイスに対応するアクティベーション ファクトリを作成します。

   [!code-cpp[wrl-consume-event#5](../codesnippet/CPP/how-to-handle-events-using-wrl_5.cpp)]

   Windows ランタイムは、完全修飾名を使用して型を識別します。 パラメーターは、 `RuntimeClass_Windows_Devices_Enumeration_DeviceInformation` Windows ランタイムによって提供される文字列であり、必要なランタイムクラス名が含まれています。

6. `IDeviceWatcher` オブジェクトを作成します。

   [!code-cpp[wrl-consume-event#6](../codesnippet/CPP/how-to-handle-events-using-wrl_6.cpp)]

7. `Callback` 関数を使用して `Added`、`EnumerationCompleted`、および `Stopped` の各イベントをサブスクライブします。

   [!code-cpp[wrl-consume-event#8](../codesnippet/CPP/how-to-handle-events-using-wrl_7.cpp)]

   `Added` イベント ハンドラーは、列挙されたデバイス数をインクリメントします。 デバイスが10 個検出されると、列挙プロセスが停止します。

   `Stopped` イベント ハンドラーは、イベント ハンドラーを削除し、完了イベントを設定します。

   `EnumerationCompleted` イベント ハンドラーは、列挙プロセスを停止します。 このイベントはデバイスの数が 10 未満である場合に処理されます。

   > [!TIP]
   > この例では、ラムダ式を使用してコールバックを定義します。 関数オブジェクト (ファンクター)、関数ポインター、または [std:: function](../../standard-library/function-class.md) オブジェクトを使用することもできます。 ラムダ式について詳しくは、「[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)」をご覧ください。

8. 列挙プロセスを開始します。

   [!code-cpp[wrl-consume-event#9](../codesnippet/CPP/how-to-handle-events-using-wrl_8.cpp)]

9. 列挙プロセスが完了するのを待機し、メッセージを出力します。 すべての `ComPtr` オブジェクトと RAII オブジェクトは自動的にスコープから外れて解放されます。

   [!code-cpp[wrl-consume-event#10](../codesnippet/CPP/how-to-handle-events-using-wrl_9.cpp)]

完全な例を次に示します。

[!code-cpp[wrl-consume-event#1](../codesnippet/CPP/how-to-handle-events-using-wrl_10.cpp)]

## <a name="compiling-the-code"></a>コードのコンパイル

コードをコンパイルするには、コードをコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付けて `wrl-consume-events.cpp` から、 **visual Studio のコマンドプロンプト** ウィンドウで次のコマンドを実行します。

`cl.exe wrl-consume-events.cpp runtimeobject.lib`

## <a name="see-also"></a>関連項目

[Windows ランタイム C++ テンプレート ライブラリ (WRL)](windows-runtime-cpp-template-library-wrl.md)
