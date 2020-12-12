---
description: '詳細については、「方法: WRL を使用して非同期操作を完了する」を参照してください。'
title: '方法: WRL を使用して非同期操作を完了する'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 02173eae-731b-49bc-b412-f1f69388b99d
ms.openlocfilehash: f8c929d737f113d995b5d171896517b3d94a6aa4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124593"
---
# <a name="how-to-complete-asynchronous-operations-using-wrl"></a>方法: WRL を使用して非同期操作を完了する

このドキュメントでは、Windows ランタイム C++ テンプレートライブラリ (WRL) を使用して非同期操作を開始し、操作の完了時に処理を実行する方法について説明します。

このドキュメントでは、2 つの例を示します。 最初の例では、非同期タイマーを開始し、そのタイマーが期限切れになるのを待機します。 この例では、タイマー オブジェクトを作成するときに、非同期アクションを指定します。 2 番目の例では、バックグラウンド ワーカー スレッドを実行します。 この例では、インターフェイスを返す Windows ランタイムメソッドを使用する方法を示し `IAsyncInfo` ます。 [コールバック](callback-function-wrl.md)関数は、非同期操作の結果を処理するイベントハンドラーを指定できるようにするため、両方の例の重要な部分です。

コンポーネントのインスタンスを作成してプロパティ値を取得する、より基本的な例については、「 [方法: Windows ランタイムコンポーネントをアクティブ化して使用](how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)する」を参照してください。

> [!TIP]
> これらの例では、コールバックを定義するためにラムダ式を使用します。 関数オブジェクト (ファンクター)、関数ポインター、または [std:: function](../../standard-library/function-class.md) オブジェクトを使用することもできます。 C++ のラムダ式の詳細については、「 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)」を参照してください。

## <a name="example-working-with-a-timer"></a>例: タイマーを使用した作業

以下の手順では、非同期タイマーを開始し、そのタイマーが期限切れになるのを待機します。 完全な例を次に示します。

> [!WARNING]
> 通常は、ユニバーサル Windows プラットフォーム (UWP) アプリで Windows ランタイム C++ テンプレートライブラリを使用しますが、この例ではコンソールアプリを使用して説明します。 などの関数 `wprintf_s` は、UWP アプリからは使用できません。 UWP アプリで使用できる型と関数の詳細については、「 [ユニバーサル Windows プラットフォームアプリでサポートされない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) 」および「 [Uwp アプリの Win32 および COM](/uwp/win32-and-com/win32-and-com-for-uwp-apps)」を参照してください。

1. 必須の `#include` Windows ランタイム、Windows ランタイム C++ テンプレートライブラリ、または C++ 標準ライブラリのヘッダーを含めます。

   [!code-cpp[wrl-consume-async#2](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_1.cpp)]

   `Windows.System.Threading.h` 非同期タイマーを使用するために必要な型を宣言します。

   コードを読みやすくするために、.cpp ファイルでは `using namespace` ディレクティブを使用することをお勧めします。

2. Windows ランタイムを初期化します。

   [!code-cpp[wrl-consume-async#3](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_2.cpp)]

3. `ABI::Windows::System::Threading::IThreadPoolTimer` インターフェイスに対応するアクティベーション ファクトリを作成します。

   [!code-cpp[wrl-consume-async#4](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_3.cpp)]

   Windows ランタイムは、完全修飾名を使用して型を識別します。 パラメーターは、 `RuntimeClass_Windows_System_Threading_ThreadPoolTimer` Windows ランタイムによって提供される文字列であり、必要なランタイムクラス名が含まれています。

4. タイマーコールバックをメインアプリに同期する [イベント](event-class-wrl.md) オブジェクトを作成します。

   [!code-cpp[wrl-consume-async#5](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_4.cpp)]

   > [!NOTE]
   > このイベントは、コンソール アプリケーションの一部としてデモのみを目的としています。 この例では、アプリケーションが終了する前に非同期操作が完了したことを確認するために、イベントを使用します。 ほとんどのアプリケーションでは、通常は非同期操作の完了を待機しません。

5. 2 秒後に期限切れになる `IThreadPoolTimer` オブジェクトを作成します。 `Callback` 関数を使用して、イベント ハンドラー (`ABI::Windows::System::Threading::ITimerElapsedHandler` オブジェクト) を作成します。

   [!code-cpp[wrl-consume-async#6](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_5.cpp)]

6. メッセージをコンソールに出力し、タイマーからのコールバックが完了するのを待機します。 すべての `ComPtr` オブジェクトと RAII オブジェクトは自動的にスコープから外れて解放されます。

   [!code-cpp[wrl-consume-async#7](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_6.cpp)]

完全な例を次に示します。

[!code-cpp[wrl-consume-async#1](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_7.cpp)]

### <a name="compiling-the-code"></a>コードのコンパイル

コードをコンパイルするには、コードをコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付けて `wrl-consume-async.cpp` から、Visual studio のコマンドプロンプトウィンドウで次のコマンドを実行します。

`cl.exe wrl-consume-async.cpp runtimeobject.lib`

## <a name="example-working-with-a-background-thread"></a>例: バックグラウンド スレッドを使用した作業

以下の手順では、ワーカー スレッドを開始し、そのスレッドによって実行されるアクションを定義します。 完全な例を次に示します。

> [!TIP]
> この例では、`ABI::Windows::Foundation::IAsyncAction` インターフェイスを使用して作業する方法を示します。 `IAsyncInfo`、`IAsyncAction`、`IAsyncActionWithProgress`、`IAsyncOperation`、および `IAsyncOperationWithProgress` を実装するすべてのインターフェイスに、このパターンを追加できます。

1. 必須の `#include` Windows ランタイム、Windows ランタイム C++ テンプレートライブラリ、または C++ 標準ライブラリのヘッダーを含めます。

   [!code-cpp[wrl-consume-asyncOp#2](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_8.cpp)]

   Windows.System.Threading.h は、ワーカー スレッドを使用するために必要な型を宣言します。

   コードを読みやすくするために、.cpp ファイルでは `using namespace` ディレクティブを使用することをお勧めします。

2. Windows ランタイムを初期化します。

   [!code-cpp[wrl-consume-asyncOp#3](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_9.cpp)]

3. `ABI::Windows::System::Threading::IThreadPoolStatics` インターフェイスに対応するアクティベーション ファクトリを作成します。

   [!code-cpp[wrl-consume-asyncOp#4](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_10.cpp)]

4. ワーカースレッドの完了をメインアプリに同期する [イベント](event-class-wrl.md) オブジェクトを作成します。

   [!code-cpp[wrl-consume-asyncOp#5](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_11.cpp)]

   > [!NOTE]
   > このイベントは、コンソール アプリケーションの一部としてデモのみを目的としています。 この例では、アプリケーションが終了する前に非同期操作が完了したことを確認するために、イベントを使用します。 ほとんどのアプリケーションでは、通常は非同期操作の完了を待機しません。

5. ワーカー スレッドを作成するには、`IThreadPoolStatics::RunAsync` メソッドを呼び出します。 アクションを定義するには、`Callback` 関数を使用します。

   [!code-cpp[wrl-consume-asyncOp#6](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_12.cpp)]

   `IsPrime` 関数は、この後に続く完全な例で定義します。

6. メッセージをコンソールに出力し、スレッドが完了するのを待機します。 すべての `ComPtr` オブジェクトと RAII オブジェクトは自動的にスコープから外れて解放されます。

   [!code-cpp[wrl-consume-asyncOp#7](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_13.cpp)]

完全な例を次に示します。

[!code-cpp[wrl-consume-asyncOp#1](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_14.cpp)]

### <a name="compiling-the-code"></a>コードのコンパイル

コードをコンパイルするには、コードをコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付けて `wrl-consume-asyncOp.cpp` から、 **visual Studio のコマンドプロンプト** ウィンドウで次のコマンドを実行します。

`cl.exe wrl-consume-asyncOp.cpp runtimeobject.lib`

## <a name="see-also"></a>関連項目

[Windows ランタイム C++ テンプレート ライブラリ (WRL)](windows-runtime-cpp-template-library-wrl.md)
