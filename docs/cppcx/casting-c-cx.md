---
title: キャスト (C + + CX) |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 5247f6c7-6a0a-4021-97c9-21c868bd9455
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f71be537ecc0dc0cb58a3ada13612dbe8cbd7d3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="casting-ccx"></a>キャスト (C++/CX)
次の 4 つの異なるキャスト演算子は、Windows ランタイム型へ適用: [static_cast 演算子](../cpp/static-cast-operator.md)、 [dynamic_cast 演算子](../cpp/dynamic-cast-operator.md)、 **safe_cast Operator**、および[reinterpret_cast 演算子](../cpp/reinterpret-cast-operator.md)です。 `safe_cast` と `static_cast` は、変換を実行できない場合に例外をスローします。 [static_cast 演算子](../cpp/static-cast-operator.md) は、コンパイル時の型チェックも実行します。 `dynamic_cast` は、型を変換できない場合 `nullptr` を返します。 `reinterpret_cast` は NULL 以外の値を返しますが、その値が無効な場合があります。 この理由で、キャストが成功することがわかっている場合を除き、 `reinterpret_cast` を使用しないことをお勧めします。 さらに、ことをお勧め、C + C スタイルのキャストを使用しないこと + CX コードと同じであるため`reinterpret_cast`です。  
  
 コンパイラとランタイムは、暗黙的なキャストも実行します。たとえば、ボックス化操作で、パラメーターの型が `Object^`であるメソッドに値型または組み込み型が引数として渡される場合です。 理論的には、暗黙的なキャストは実行時に例外を引き起こしません。コンパイラが暗黙的な変換を実行できない場合は、コンパイル時にエラーが発生します。  
  
Windows ランタイムは、例外の代わりに HRESULT エラー コードを使用して COM を抽象です。 一般に、 [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) は E_NOINTERFACE の低レベルの COM エラーを表します。  
  
## <a name="staticcast"></a>static_cast  
 コンパイル時に `static_cast` をチェックすることで、2 つの型の間に継承関係が存在するかどうかを判断します。 2 つの型に継承関係がない場合は、キャストによってコンパイラ エラーが発生します。  
  
 ref クラスの `static_cast` は、ランタイムのチェックも実行します。 ref クラスに対する `static_cast` はコンパイル時の検証でエラーになりませんが、実行時にはエラーになります。この場合、 `Platform::InvalidCastException` がスローされます。 一般的に、このような例外を処理する必要はありません。ほとんどの例外は常に、開発時およびテスト時に解決できるプログラミング エラーを示しているためです。  
  
 2 つの型の間の関係をコードが明示的に宣言し、したがってキャストが機能することを確信している場合は、 `static_cast` を使用します。  
  
```
    interface class A{};  
    public ref class Class1 sealed : A { };  
...  
    A^ obj = ref new Class1(); // Class1 is an A  
    // You know obj is a Class1. The compiler verifies that this is possible, and in C++/CX a run-time check is also performed.  
    Class1^ c = static_cast<Class1^>(obj);
```  
  
## <a name="safecast"></a>safe_cast  
 `safe_cast`演算子は一部 ofWindows ランタイム。 変換が失敗すると、実行時の型チェックを実行して `Platform::InvalidCastException` をスローします。 ランタイム エラーが例外条件を示している場合は `safe_cast` を使用します。 `safe_cast` の主な目的は、開発フェーズおよびテスト フェーズにおけるプログラミング エラーを発生時点で識別しやすくすることです。 ハンドルされていない例外自体がエラーの位置を示しているため、例外を処理する必要はありません。  
  
 コードが関係を宣言していないが、キャストが機能することを確信している場合は、safe_cast を使用します。  
  
```  
    // A and B are not related  
    interface class A{};  
    interface class B{};  
    public ref class Class1 sealed : A, B { };  
...  
    A^ obj = ref new Class1();  
  
    // You know that obj’s backing type implements A and B, but  
    // the compiler can’t tell this by comparing A and B. The run-time type check succeeds.  
    B^ obj2 = safe_cast<B^>(obj);  
```  
  
## <a name="dynamiccast"></a>dynamic_cast  
 使用して`dynamic_cast`オブジェクトをキャストするとき (hat では具体的には、 `^`) をより強い派生型にする期待いるか、ターゲット オブジェクトで生じる可能性もあります`nullptr`すなわち、キャストが失敗して通常のコードとその状況を処理します。例外の代わりにパスします。 たとえば、**空のアプリケーション (ユニバーサル Windows)** プロジェクト テンプレートを`OnLaunched`メソッドで`app.xamp.cpp`を使用して`dynamic_cast`アプリ ウィンドウにコンテンツがあるかどうかをテストします。 コンテンツが含まれていなくても、エラーではありません。これは予期された状態です。 `Windows::Current::Content` は `Windows::UI::XAML::UIElement` であり、継承階層内のより強い派生型である `Windows::UI.XAML::Controls::Frame`への変換が実行されます。  
```
void App::OnLaunched(Windows::ApplicationModel::Activation::LaunchActivatedEventArgs^ args)  
{  
    auto rootFrame = dynamic_cast<Frame^>(Window::Current->Content);  
  
    // Do not repeat app initialization when the window already has content,  
    // just ensure that the window is active  
    if (rootFrame == nullptr)  
    {  
        // Create a Frame to act as the navigation context and associate it with  
        // a SuspensionManager key  
        rootFrame = ref new Frame();  
...  
```  
 `dynamic_cast` のもう 1 つの用途は、ボックス化された値型を持つかどうかを判断するために `Object^` を調べることです。 この場合、 `dynamic_cast<Platform::Box>` または `dynamic_cast<Platform::IBox>`を試行します。  
  
 **dynamic_cast と追跡参照 (%)**  
  
 `dynamic_cast` を追跡参照に適用することもできますが、この場合キャストは `safe_cast`と同様に動作します。 追跡参照は `Platform::InvalidCastException` の値を持つことができないため、エラーが発生した場合は `nullptr`をスローします。  
  
## <a name="reinterpretcast"></a>reinterpret_cast  
 [reinterpret_cast](../cpp/reinterpret-cast-operator.md) を使用しないことをお勧めします。コンパイル時のチェックと、ランタイム チェックのどちらも実行されないためです。 最悪の状況では、 `reinterpret_cast` を使用すると開発時にプログラミング エラーが検出されず、プログラムの動作に軽度または致命的なエラーが発生するおそれがあります。 したがって、関係のない型の間でキャストを実行する必要があり、そのキャストが正常に実行される確証があるという非常にまれな状況でのみ、 `reinterpret_cast` を使用することをお勧めします。 まれな使用の例は aWindows ランタイム型を基になる ABI の型に変換する: これは、オブジェクトに対する参照カウントの制御をかかっていることを意味します。 この作業を行うには、 [ComPtr Class](../cpp/com-ptr-t-class.md) のスマート ポインターを使用することをお勧めします。 それ以外の場合、特にインターフェイスに対して Release を呼び出す必要があります。 次の例では、ref クラスを `IInspectable*`にキャストする方法を示します。  
  
```  
#include <wrl.h>  
using namespace Microsoft::WRL;  
auto winRtObject = ref new SomeWinRTType();  
ComPtr<IInspectable> inspectable = reinterpret_cast<IInspectable*>(winRtObject);  
...
```  
  
 使用する場合`reinterpret_cast`oneWindows ランタイム インターフェイスからの変換を 2 回解放するオブジェクトが発生します。 したがって、[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] 以外のインターフェイスを変換する場合にのみ、このキャストを使用します。  
  
 **ABI の型**  
  
-   ABI の型は、Windows SDK のヘッダーに置かれます。 判別しやすいように、ヘッダーは名前空間にちなんだ名前が付けられています ( `windows.storage.h`など)。  
  
-   ABI の型は、 `ABI::Windows::Storage::Streams::IBuffer*`のような特殊な ABI 名前空間に置かれます。  
  
-   AWindows ランタイム インターフェイスの種類と、同等の ABI の型の間の変換は常に安全、つまり、`IBuffer^`に`ABI::IBuffer*`です。  
  
-   AWindows ランタイム ランタイム クラスに常に変換する`IInspectable*`またはわかっている場合、既定のインターフェイスです。  
  
-   ABI の型への変換後は、その型の有効期間を管理し、COM 規則に従う必要があります。 ABI のポインターの有効期間管理を容易にするために、 `WRL::ComPtr` を使用することをお勧めします。  
  
 次の表に、 `reinterpret_cast`を使用しても安全な状況の概要を示します。 どの状況でも、キャストは両方向とも安全です。  
  
|||  
|-|-|  
|HSTRING|String^|  
|HSTRING*|String^*|  
|IInspectable*|Object^|  
|IInspectable**|Object^*|  
|IInspectable-derived-type*|same-interface-from-winmd^|  
|IInspectable-derived-type**|same-interface-from-winmd^*|  
|IDefault-interface-of-RuntimeClass*|same-RefClass-from-winmd^|  
|IDefault-interface-of-RuntimeClass**|same-RefClass-from-winmd^*|  
  
## <a name="see-also"></a>関連項目  
 [型システム](../cppcx/type-system-c-cx.md)   
 [Visual C 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)   
 [名前空間参照](../cppcx/namespaces-reference-c-cx.md)
