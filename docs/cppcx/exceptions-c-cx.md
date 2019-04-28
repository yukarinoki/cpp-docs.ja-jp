---
title: 例外 (C++/CX)
ms.date: 01/18/2018
ms.assetid: 6cbdc1f1-e4d7-4707-a670-86365146432f
ms.openlocfilehash: 7134cbb9e90f0355a3b2a912330027cf73876443
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301527"
---
# <a name="exceptions-ccx"></a>例外 (C++/CX)

エラー処理 c++/cli CX は例外に基づいています。 最も基本的なレベルでは、Windows ランタイム コンポーネントは、HRESULT 値としてエラーを報告します。 C++/cli CX、これらの値は HRESULT 値をプログラムでアクセスできる文字列による説明が含まれている厳密に型指定された例外に変換されます。  例外は、 `ref class` から派生した `Platform::Exception`として実装されます。  `Platform` 名前空間は、ほとんどの共通 HRESULT 値のために異なる例外クラスを定義します。それ以外のすべての値は、 `Platform::COMException` クラスで報告されます。 すべての例外クラスには、元の HRESULT を取得するために使用できる [Exception::HResult](platform-exception-class.md#hresult) フィールドがあります。 C++ 以外の言語で記述されたコードで、生成された場合でも、例外の元のソースの特定に役立つことができます、デバッガーでのユーザー コードに関するコール スタック情報を確認することもできます。

## <a name="exceptions"></a>例外

C++ プログラムでスローおよび Windows ランタイム操作から派生したから派生した例外をキャッチ`std::exception`、またはユーザー定義型です。 アプリケーション バイナリ インターフェイス (ABI) の境界を越えるなど、例外をキャッチするコードが JavaScript で記述されたときに場合にのみ、Windows ランタイムの例外をスローする必要があります。 ときに、非 Windows ランタイムC++例外が ABI 境界に達すると、例外に変換される、 `Platform::FailureException` 、E_FAIL HRESULT を表す例外。 ABI の詳細については、「 [Creating Windows Runtime Components in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)」を参照してください。

宣言することができます、 [platform::exception](platform-exception-class.md)を HRESULT パラメーター、または HRESULT パラメーターを受け取る 2 つのコンス トラクターのいずれかを使用して、 [platform::string](platform-string-class.md)^ パラメーター間で渡すことができますが、これを処理するすべての Windows ランタイム アプリに ABI です。 または、1 つの HRESULT パラメーター、または 1 つの HRESULT パラメーターと [パラメーターのいずれかを受け取る 2 つの](platform-exception-class.md#createexception) Exception::CreateException メソッド `Platform::String^` オーバーロードの 1 つを使用して、例外を宣言できます。

## <a name="standard-exceptions"></a>標準の例外

C++/CX では、一般的な HRESULT エラーを表す標準の例外のセットをサポートします。 この標準例外は [Platform::COMException](platform-comexception-class.md)から派生し、その例外は `Platform::Exception`から派生します。 ABI の境界を越えて例外をスローするときは、標準の例外の 1 つをスローする必要があります。

`Platform::Exception`から独自の例外の種類を派生させることはできません。 カスタム例外をスローするには、ユーザー定義の HRESULT を使用して `COMException` オブジェクトを構築します。

次の表は、標準の例外の一覧を示しています。

|名前|基になる HRESULT|説明|
|----------|------------------------|-----------------|
|COMException|*ユーザー定義の hresult*|COM メソッドの呼び出しから認識されない HRESULT が返されるとスローされます。|
|AccessDeniedException|E\_ACCESSDENIED|リソースや機能へのアクセスが拒否されるとスローされます。|
|ChangedStateException|E\_CHANGED\_状態|コレクション反復子またはコレクション ビューのメソッドが、親コレクションの変更後に呼び出さたときにスローされます。これにより、メソッドの結果は無効になります。|
|ClassNotRegisteredException|REGDB\_E\_CLASSNOTREG|COM クラスが登録されていないときにスローされます。|
|DisconnectedException|RPC\_E\_切断|オブジェクトがクライアントから接続を切断されるとスローされます。|
|FailureException|E\_失敗|操作が失敗したときにスローされます。|
|InvalidArgumentException|E\_INVALIDARG|メソッドに提供された引数のいずれかが有効でない場合にスローされます。|
|InvalidCastException|E\_NOINTERFACE|型が別の型にキャストできないときにスローされます。|
|NotImplementedException|E\_NOTIMPL|インターフェイス メソッドがクラスに実装されていないときにスローされます。|
|NullReferenceException|E\_ポインター|null オブジェクト参照を逆参照しようするとスローされます。|
|ObjectDisposedException|RO\_E\_終了|破棄されたオブジェクトで操作が実行されるとスローされます。|
|OperationCanceledException|E\_中止|操作が中止されるとスローされます。|
|OutOfBoundsException|E\_境界|操作が有効範囲外のデータにアクセスを試みるとスローされます。|
|OutOfMemoryException|E\_OUTOFMEMORY|メモリが不足して操作を完了できないときにスローされます。|
|WrongThreadException|RPC\_E\_間違った\_スレッド|スレッドが、スレッドのアパートメントに属さないプロキシ オブジェクト用のインターフェイス ポインターを通じて呼び出すときにスローされます。|

## <a name="hresult-and-message-properties"></a>HResult および Message プロパティ

すべての例外に、 [HResult](platform-comexception-class.md#hresult) プロパティと [Message](platform-comexception-class.md#message) プロパティがあります。 [Exception::HResult](platform-exception-class.md#hresult) プロパティは、例外の基になる数値 HRESULT 値を取得します。 [Exception::Message](platform-exception-class.md#message) プロパティは、例外を記述するシステム指定文字列を取得します。 Windows 8 では、メッセージは、デバッガーでのみ使用でき、読み取り専用。 これは、例外を再スローするときに、例外を変更できないことを意味します。 Windows 8.1 では、例外を再スローする場合に、プログラムでメッセージの文字列にアクセスし、新しいメッセージを提供することができます。 非同期メソッド呼び出しに関する呼び出し履歴を含め、より詳細な呼び出し履歴情報もデバッガーで使用できます。

### <a name="examples"></a>使用例

この例では、同期操作の Windows ランタイムの例外をスローする方法を示します。

[!code-cpp[cx_exceptions#01](codesnippet/CPP/exceptiontest/class1.cpp#01)]

次の例は、例外をキャッチする方法を示しています。

[!code-cpp[cx_exceptions#02](codesnippet/CPP/exceptiontest/class1.cpp#02)]

非同期操作中にスローされる例外をキャッチするには、タスク クラスを使用し、エラー処理の継続を追加します。 エラー処理コードの継続は、他のスレッドでスローされる例外を呼び出し元のスレッドにマーシャリングして、発生する可能性があるすべての例外をコード中の 1 つのポイントで処理できるようにします。 詳しくは、「 [C++ での非同期プログラミング](/windows/uwp/threading-async/asynchronous-programming-in-cpp-universal-windows-platform-apps)」を参照してください。

## <a name="unhandlederrordetected-event"></a>UnhandledErrorDetected イベント

Windows 8.1 でにサブスクライブすることができます、 [:unhandlederrordetected](/uwp/api/windows.applicationmodel.core.icoreapplicationunhandlederror#Windows_ApplicationModel_Core_ICoreApplicationUnhandledError_UnhandledErrorDetected)プロセスが停止される未処理のエラーへのアクセスを提供する、静的イベント。 エラーがどこで発生したかにかかわりなく、イベントの引数によって渡される [Windows::ApplicationModel::Core::UnhandledError](/uwp/api/windows.applicationmodel.core.unhandlederror) オブジェクトという形で、このハンドラーに到達します。 オブジェクトに対して `Propagate` を呼び出した場合、エラー コードに対応する型の `Platform::*Exception` が生成され、スローされます。 catch ブロックで、必要に応じて、ユーザー状態を保存することができ、その後、プロセスが `throw`を呼び出して終了すること、またはプログラムを既知の状態に戻すために他の作業を実行することを許可できます。 次の例に、基本的なパターンを示します。

で app.xaml.h:

```cpp
void OnUnhandledException(Platform::Object^ sender, Windows::ApplicationModel::Core::UnhandledErrorDetectedEventArgs^ e);
```

で app.xaml.cpp:

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

### <a name="remarks"></a>Remarks

C++/CX が使用しない、`finally`句。

## <a name="see-also"></a>関連項目

[Visual C 言語リファレンス](visual-c-language-reference-c-cx.md)<br/>
[名前空間参照](namespaces-reference-c-cx.md)
