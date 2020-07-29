---
title: 例外 (C++/CX)
ms.date: 07/02/2019
ms.assetid: 6cbdc1f1-e4d7-4707-a670-86365146432f
ms.openlocfilehash: 7b4475cfa92aa952dd5a2996508d9343255b7ed2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231014"
---
# <a name="exceptions-ccx"></a>例外 (C++/CX)

C++/CX でのエラー処理は、例外に基づいています。 最も基本的なレベルでは、Windows ランタイムコンポーネントは、HRESULT 値としてエラーを報告します。 C++/CX では、これらの値は、HRESULT 値と、プログラムでアクセスできる文字列の説明を含む厳密に型指定された例外に変換されます。  例外は、から派生したとして実装され **`ref class`** `Platform::Exception` ます。  `Platform` 名前空間は、ほとんどの共通 HRESULT 値のために異なる例外クラスを定義します。それ以外のすべての値は、 `Platform::COMException` クラスで報告されます。 すべての例外クラスには、元の HRESULT を取得するために使用できる [Exception::HResult](platform-exception-class.md#hresult) フィールドがあります。 また、C++ 以外の言語で記述されたコードで発生した場合でも、例外の元のソースを特定するのに役立つ、デバッガーでのユーザーコードのコールスタック情報を調べることもできます。

## <a name="exceptions"></a>例外

C++ プログラムでは、Windows ランタイム操作、から派生した例外、 `std::exception` またはユーザー定義型からの例外をスローしてキャッチできます。 Windows ランタイム例外をスローする必要があるのは、例外をキャッチするコードが JavaScript で記述されている場合など、アプリケーションバイナリインターフェイス (ABI) の境界を越える場合のみです。 非 Windows ランタイム C++ 例外が ABI 境界に達すると、例外は、E_FAIL HRESULT を表す例外に変換され `Platform::FailureException` ます。 ABI の詳細については、「 [Creating Windows Runtime Components in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)」を参照してください。

HRESULT パラメーターを受け取る2つのコンストラクターのいずれかを使用するか、または HRESULT パラメーターと、それを処理する任意の Windows ランタイムアプリに ABI を介して渡すことができる[platform:: String](platform-string-class.md)^ パラメーターを使用して、 [Platform:: Exception](platform-exception-class.md)を宣言できます。 または、1 つの HRESULT パラメーター、または 1 つの HRESULT パラメーターと [パラメーターのいずれかを受け取る 2 つの](platform-exception-class.md#createexception) Exception::CreateException メソッド `Platform::String^` オーバーロードの 1 つを使用して、例外を宣言できます。

## <a name="standard-exceptions"></a>標準の例外

C++/CX は、一般的な HRESULT エラーを表す標準の例外のセットをサポートしています。 この標準例外は [Platform::COMException](platform-comexception-class.md)から派生し、その例外は `Platform::Exception`から派生します。 ABI の境界を越えて例外をスローするときは、標準の例外の 1 つをスローする必要があります。

`Platform::Exception`から独自の例外の種類を派生させることはできません。 カスタム例外をスローするには、ユーザー定義の HRESULT を使用して `COMException` オブジェクトを構築します。

次の表は、標準の例外の一覧を示しています。

|名前|基になる HRESULT|[説明]|
|----------|------------------------|-----------------|
|COMException|*ユーザー定義の hresult*|COM メソッドの呼び出しから認識されない HRESULT が返されるとスローされます。|
|AccessDeniedException|E \_ ACCESSDENIED|リソースや機能へのアクセスが拒否されるとスローされます。|
|ChangedStateException|E \_ 変更された \_ 状態|コレクション反復子またはコレクション ビューのメソッドが、親コレクションの変更後に呼び出さたときにスローされます。これにより、メソッドの結果は無効になります。|
|ClassNotRegisteredException|REGDB \_ E \_ CLASSNOTREG|COM クラスが登録されていないときにスローされます。|
|DisconnectedException|RPC が切断されました \_ \_|オブジェクトがクライアントから接続を切断されるとスローされます。|
|FailureException|E \_ 失敗|操作が失敗したときにスローされます。|
|InvalidArgumentException|E \_ INVALIDARG|メソッドに提供された引数のいずれかが有効でない場合にスローされます。|
|InvalidCastException|E \_ NOINTERFACE|型が別の型にキャストできないときにスローされます。|
|NotImplementedException|E \_ NOTIMPL|インターフェイス メソッドがクラスに実装されていないときにスローされます。|
|NullReferenceException|E \_ ポインター|null オブジェクト参照を逆参照しようするとスローされます。|
|ObjectDisposedException|RO \_ E \_ 終了|破棄されたオブジェクトで操作が実行されるとスローされます。|
|OperationCanceledException|E \_ 中止|操作が中止されるとスローされます。|
|OutOfBoundsException|E \_ 境界|操作が有効範囲外のデータにアクセスを試みるとスローされます。|
|OutOfMemoryException|E \_ OUTOFMEMORY|メモリが不足して操作を完了できないときにスローされます。|
|WrongThreadException|RPC \_ に \_ 間違ったスレッドがあります \_|スレッドが、スレッドのアパートメントに属さないプロキシ オブジェクト用のインターフェイス ポインターを通じて呼び出すときにスローされます。|

## <a name="hresult-and-message-properties"></a>HResult および Message プロパティ

すべての例外に、 [HResult](platform-comexception-class.md#hresult) プロパティと [Message](platform-comexception-class.md#message) プロパティがあります。 [Exception::HResult](platform-exception-class.md#hresult) プロパティは、例外の基になる数値 HRESULT 値を取得します。 [Exception::Message](platform-exception-class.md#message) プロパティは、例外を記述するシステム指定文字列を取得します。 Windows 8 では、メッセージはデバッガーでのみ使用でき、読み取り専用です。 これは、例外を再スローするときに、例外を変更できないことを意味します。 Windows 8.1 では、例外を再スローする場合に、プログラムでメッセージの文字列にアクセスし、新しいメッセージを提供することができます。 非同期メソッド呼び出しに関する呼び出し履歴を含め、より詳細な呼び出し履歴情報もデバッガーで使用できます。

### <a name="examples"></a>例

次の例では、同期操作の Windows ランタイム例外をスローする方法を示します。

[!code-cpp[cx_exceptions#01](codesnippet/CPP/exceptiontest/class1.cpp#01)]

次の例は、例外をキャッチする方法を示しています。

[!code-cpp[cx_exceptions#02](codesnippet/CPP/exceptiontest/class1.cpp#02)]

非同期操作中にスローされた例外をキャッチするには、タスククラスを使用して、エラー処理の継続を追加します。 エラー処理コードの継続は、他のスレッドでスローされる例外を呼び出し元のスレッドにマーシャリングして、発生する可能性があるすべての例外をコード中の 1 つのポイントで処理できるようにします。 詳しくは、「 [C++ での非同期プログラミング](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps)」を参照してください。

## <a name="unhandlederrordetected-event"></a>UnhandledErrorDetected イベント

Windows 8.1 では、 [Windows:: ApplicationModel:: Core:: CoreApplication:: UnhandledErrorDetected](/uwp/api/windows.applicationmodel.core.icoreapplicationunhandlederror.unhandlederrordetected)静的イベントをサブスクライブできます。このイベントは、プロセスを停止しようとしている未処理のエラーへのアクセスを提供します。 エラーがどこで発生したかにかかわりなく、イベントの引数によって渡される [Windows::ApplicationModel::Core::UnhandledError](/uwp/api/windows.applicationmodel.core.unhandlederror) オブジェクトという形で、このハンドラーに到達します。 オブジェクトに対して `Propagate` を呼び出した場合、エラー コードに対応する型の `Platform::*Exception` が生成され、スローされます。 Catch ブロックでは、必要に応じてユーザー状態を保存してから、を呼び出してプロセスを終了するか **`throw`** 、またはプログラムを既知の状態に戻すために何らかの処理を実行することができます。 次の例に、基本的なパターンを示します。

App.xaml の場合:

```cpp
void OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e);
```

App.xaml で、次のようにします。

```cpp
// Subscribe to the event, for example in the app class constructor:
Windows::ApplicationModel::Core::CoreApplication::UnhandledErrorDetected += ref new EventHandler<UnhandledErrorDetectedEventArgs^>(this, &App::OnUnhandledException);

// Event handler implementation:
void App::OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e)
{
    auto err = e->UnhandledError;

    if (!err->Handled) //Propagate has not been called on it yet.
{
    try
    {
        err->Propagate();
    }
    // Catch any specific exception types if you know how to handle them
    catch (AccessDeniedException^ ex)
    {
        // TODO: Log error and either take action to recover
        // or else re-throw exception to continue fail-fast
    }
}
```

### <a name="remarks"></a>解説

C++/CX は句を使用しません **`finally`** 。

## <a name="see-also"></a>関連項目

[C++/CX 言語リファレンス](visual-c-language-reference-c-cx.md)<br/>
[名前空間のリファレンス](namespaces-reference-c-cx.md)
