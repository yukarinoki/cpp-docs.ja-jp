---
title: キャスト (C + + CX) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/19/2018
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 5247f6c7-6a0a-4021-97c9-21c868bd9455
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 66c0e6bc9d987c400c709e74586e6e37ccc0b715
ms.sourcegitcommit: 301bb19056e5bae84ff50f7d1df1e546efe225ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2018
ms.locfileid: "36305996"
---
# <a name="casting-ccx"></a>キャスト (C++/CX)

次の 4 つの異なるキャスト演算子は、Windows ランタイム型へ適用: [static_cast 演算子](../cpp/static-cast-operator.md)、 [dynamic_cast 演算子](../cpp/dynamic-cast-operator.md)、 **safe_cast Operator**、および[reinterpret_cast 演算子](../cpp/reinterpret-cast-operator.md)です。 **safe_cast**と**static_cast**は変換を実行できないときに例外をスロー[static_cast 演算子](../cpp/static-cast-operator.md)コンパイル時の型チェックも実行します。 **dynamic_cast**返します**nullptr**型変換に失敗した場合。 **Reinterpret_cast** null 以外の値を返す有効でない可能性があります。 このため、ことをお勧めは使用しないこと**reinterpret_cast**キャストが成功することがわかっていない限り、します。 さらに、ことをお勧め、C + の C スタイルのキャストを使用しないこと + CX コードと同じであるため**reinterpret_cast**です。

コンパイラとランタイムは、暗黙的なキャストも実行します。たとえば、ボックス化操作で、パラメーターの型が `Object^`であるメソッドに値型または組み込み型が引数として渡される場合です。 理論的には、暗黙的なキャストは実行時に例外を引き起こしません。コンパイラが暗黙的な変換を実行できない場合は、コンパイル時にエラーが発生します。

Windows ランタイムは、例外の代わりに HRESULT エラー コードを使用して COM を抽象です。 一般に、 [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) は E_NOINTERFACE の低レベルの COM エラーを表します。

## <a name="staticcast"></a>static_cast

A **static_cast**は 2 種類の継承関係があるかどうかを判断するコンパイル時にチェックします。 2 つの型に継承関係がない場合は、キャストによってコンパイラ エラーが発生します。

A **static_cast**で ref クラスもと、実行時のチェックを実行します。 A **static_cast** 、ref クラスはコンパイル時の検証が、実行時以外の場合はここではエラーになります、`Platform::InvalidCastException`がスローされます。 一般的に、このような例外を処理する必要はありません。ほとんどの例外は常に、開発時およびテスト時に解決できるプログラミング エラーを示しているためです。

使用して**static_cast**コードでは、次の 2 つの型間のリレーションシップを明示的に宣言し、キャストが機能することを確認しているためかどうか。

```cpp
    interface class A{};
    public ref class Class1 sealed : A { };
    // ...
    A^ obj = ref new Class1(); // Class1 is an A
    // You know obj is a Class1. The compiler verifies that this is possible, and in C++/CX a run-time check is also performed.
    Class1^ c = static_cast<Class1^>(obj);
```

## <a name="safecast"></a>safe_cast

**Safe_cast**演算子は、Windows ランタイムの一部です。 変換が失敗すると、実行時の型チェックを実行して `Platform::InvalidCastException` をスローします。 使用して**safe_cast**実行時エラーが例外条件を示している場合。 主な目的**safe_cast**開発時にプログラミング エラーを識別するのにはおよびテスト フェーズが発生した時点です。 ハンドルされていない例外自体がエラーの位置を示しているため、例外を処理する必要はありません。

コードが関係を宣言していないが、キャストが機能することを確信している場合は、safe_cast を使用します。

```cpp
    // A and B are not related
    interface class A{};
    interface class B{};
    public ref class Class1 sealed : A, B { };
    // ...
    A^ obj = ref new Class1();

    // You know that obj’s backing type implements A and B, but
    // the compiler can’t tell this by comparing A and B. The run-time type check succeeds.
    B^ obj2 = safe_cast<B^>(obj);
```

## <a name="dynamiccast"></a>dynamic_cast

使用して**dynamic_cast**オブジェクトをキャストするとき (具体的にはハット**^**) をより強い派生型にする期待いるか、ターゲット オブジェクトで生じる可能性もあります**nullptr**またはキャストが失敗して、その状況を例外ではなく標準のコード パスとして処理することです。 たとえば、**空のアプリケーション (ユニバーサル Windows)** プロジェクト テンプレート、 `OnLaunched` app.xamp.cpp でメソッド**dynamic_cast**アプリ ウィンドウにコンテンツがあるかどうかをテストします。 コンテンツが含まれていなくても、エラーではありません。これは予期された状態です。 `Windows::Current::Content` は `Windows::UI::XAML::UIElement` であり、継承階層内のより強い派生型である `Windows::UI.XAML::Controls::Frame`への変換が実行されます。

```cpp
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
        // ...
    }
}
```

別の用途**dynamic_cast**を探すには、`Object^`をボックス化された値の型が含まれているかどうかを判断します。 この場合、 `dynamic_cast<Platform::Box>` または `dynamic_cast<Platform::IBox>`を試行します。

## <a name="dynamiccast-and-tracking-references-"></a>dynamic_cast と追跡参照 (%) 

適用することも、 **dynamic_cast**のように、キャストが動作を追跡参照には、ここでは**safe_cast**です。 スロー`Platform::InvalidCastException`エラー発生時に追跡参照は、値を持つことはできませんので**nullptr**です。

## <a name="reinterpretcast"></a>reinterpret_cast

[reinterpret_cast](../cpp/reinterpret-cast-operator.md) を使用しないことをお勧めします。コンパイル時のチェックと、ランタイム チェックのどちらも実行されないためです。 最悪の場合、 **reinterpret_cast**開発時に検出されないし、プログラムの動作に軽度または致命的なエラーが発生するエラーをプログラミングできるようになります。 したがってをお勧めを使用すること**reinterpret_cast**関係のない型の間でキャストする必要があり、キャストが成功することがわかっているまれなケースでのみです。 まれな使用の例は、Windows ランタイム型を基になる ABI の型に変換する: これは、オブジェクトに対する参照カウントの制御をかかっていることを意味します。 この作業を行うには、 [ComPtr Class](../cpp/com-ptr-t-class.md) のスマート ポインターを使用することをお勧めします。 それ以外の場合、特にインターフェイスに対して Release を呼び出す必要があります。 次の例では、ref クラスを `IInspectable*`にキャストする方法を示します。

```cpp
#include <wrl.h>
using namespace Microsoft::WRL;
auto winRtObject = ref new SomeWinRTType();
ComPtr<IInspectable> inspectable = reinterpret_cast<IInspectable*>(winRtObject);
// ...
```

使用する場合**reinterpret_cast** oneWindows ランタイム インターフェイスからの変換を 2 回解放するオブジェクトが発生します。 したがって、[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] 以外のインターフェイスを変換する場合にのみ、このキャストを使用します。

## <a name="abi-types"></a>ABI の型

- ABI の型は、Windows SDK のヘッダーに置かれます。 判別しやすいように、ヘッダーは名前空間にちなんだ名前が付けられています ( `windows.storage.h`など)。

- ABI の型は、 `ABI::Windows::Storage::Streams::IBuffer*`のような特殊な ABI 名前空間に置かれます。

- Windows ランタイム インターフェイスの種類と、同等の ABI の型の間の変換は常に安全、つまり、`IBuffer^`に`ABI::IBuffer*`です。

- Windows ランタイムのランタイム クラスに常に変換する`IInspectable*`またはわかっている場合、既定のインターフェイスです。

- ABI の型への変換後は、その型の有効期間を管理し、COM 規則に従う必要があります。 ABI のポインターの有効期間管理を容易にするために、 `WRL::ComPtr` を使用することをお勧めします。

次の表を安全に使用されるケース**reinterpret_cast**です。 どの状況でも、キャストは両方向とも安全です。

|||
|-|-|
|`HSTRING`|`String^`|
|`HSTRING*`|`String^*`|
|`IInspectable*`|`Object^`|
|`IInspectable**`|`Object^*`|
|`IInspectable-derived-type*`|`same-interface-from-winmd^`|
|`IInspectable-derived-type**`|`same-interface-from-winmd^*`|
|`IDefault-interface-of-RuntimeClass*`|`same-RefClass-from-winmd^`|
|`IDefault-interface-of-RuntimeClass**`|`same-RefClass-from-winmd^*`|

## <a name="see-also"></a>関連項目

- [型システム](../cppcx/type-system-c-cx.md)
- [Visual C 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)
- [名前空間参照](../cppcx/namespaces-reference-c-cx.md)
