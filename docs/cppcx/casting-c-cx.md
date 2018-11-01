---
title: キャスト (C++/CX)
ms.date: 06/19/2018
ms.assetid: 5247f6c7-6a0a-4021-97c9-21c868bd9455
ms.openlocfilehash: 65d489d14c91b462e5a2bbe8bd60fce2657904a7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454822"
---
# <a name="casting-ccx"></a>キャスト (C++/CX)

Windows ランタイム型に 4 つの異なるキャスト演算子が適用されます: [static_cast 演算子](../cpp/static-cast-operator.md)、 [dynamic_cast Operator](../cpp/dynamic-cast-operator.md)、 **safe_cast Operator**、および[reinterpret_cast 演算子](../cpp/reinterpret-cast-operator.md)します。 **safe_cast**と**static_cast**変換を実行することはできませんが、例外をスロー[static_cast 演算子](../cpp/static-cast-operator.md)もはコンパイル時の型チェックを実行します。 **dynamic_cast**返します**nullptr**型変換に失敗した場合。 **Reinterpret_cast** null 以外の値を返す有効でない可能性があります。 このため、お勧めします使用しないこと**reinterpret_cast**キャストが成功することがわかっていない限り、します。 C++ で C スタイル キャストは使用しないこと勧めさらに、/cli CX コードと同じですが**reinterpret_cast**します。

コンパイラとランタイムは、暗黙的なキャストも実行します。たとえば、ボックス化操作で、パラメーターの型が `Object^`であるメソッドに値型または組み込み型が引数として渡される場合です。 理論的には、暗黙的なキャストは実行時に例外を引き起こしません。コンパイラが暗黙的な変換を実行できない場合は、コンパイル時にエラーが発生します。

Windows ランタイムでは、例外の代わりに HRESULT エラー コードを使用して、COM 経由で抽象化です。 一般に、 [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) は E_NOINTERFACE の低レベルの COM エラーを表します。

## <a name="staticcast"></a>static_cast

A **static_cast** 2 つの型の間に継承関係があるかどうかを判断するコンパイル時にチェックされます。 2 つの型に継承関係がない場合は、キャストによってコンパイラ エラーが発生します。

A **static_cast** ref クラスとも、実行時のチェックを実行します。 A **static_cast** ref クラスはコンパイル時の検証を渡しますが、実行時に、ここでは依然として失敗を`Platform::InvalidCastException`がスローされます。 一般的に、このような例外を処理する必要はありません。ほとんどの例外は常に、開発時およびテスト時に解決できるプログラミング エラーを示しているためです。

使用**static_cast**かどうか、コードは、2 つの型間のリレーションシップを明示的に宣言し、そのため、キャストが機能することを確認します。

```cpp
    interface class A{};
    public ref class Class1 sealed : A { };
    // ...
    A^ obj = ref new Class1(); // Class1 is an A
    // You know obj is a Class1. The compiler verifies that this is possible, and in C++/CX a run-time check is also performed.
    Class1^ c = static_cast<Class1^>(obj);
```

## <a name="safecast"></a>safe_cast

**Safe_cast**演算子は、Windows ランタイムの一部です。 変換が失敗すると、実行時の型チェックを実行して `Platform::InvalidCastException` をスローします。 使用**safe_cast**実行時エラーが例外条件を示します。 主な目的**safe_cast**開発中にプログラミング エラーを識別して、テスト フェーズが発生した時点でします。 ハンドルされていない例外自体がエラーの位置を示しているため、例外を処理する必要はありません。

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

使用**dynamic_cast**オブジェクトをキャストするとき (具体的には、hat **^**) より強い派生型に期待するか、ターゲット オブジェクトで生じる可能性もあります**nullptr**か、キャストが失敗すると、その条件を例外ではなく通常のコード パスとして処理する、または。 たとえば、**空のアプリ (ユニバーサル Windows)** プロジェクト テンプレートを`OnLaunched`app.xamp.cpp でメソッド**dynamic_cast**アプリ ウィンドウにコンテンツがあるかどうかをテストします。 コンテンツが含まれていなくても、エラーではありません。これは予期された状態です。 `Windows::Current::Content` は `Windows::UI::XAML::UIElement` であり、継承階層内のより強い派生型である `Windows::UI.XAML::Controls::Frame`への変換が実行されます。

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

適用することも、 **dynamic_cast**のように動作を追跡参照に、ここでは、キャスト**safe_cast**します。 スロー`Platform::InvalidCastException`失敗時に追跡参照は、の値を持つことはできませんので**nullptr**。

## <a name="reinterpretcast"></a>reinterpret_cast

[reinterpret_cast](../cpp/reinterpret-cast-operator.md) を使用しないことをお勧めします。コンパイル時のチェックと、ランタイム チェックのどちらも実行されないためです。 最悪の場合、 **reinterpret_cast**プログラミング開発時に検出されないに移動し、プログラムの動作に軽度または致命的なエラーが発生するエラーになります。 使用すること勧めそのため、 **reinterpret_cast**関連のない型の間でキャストする必要があり、キャストが成功することがわかっているまれなケースでのみです。 まれな使用の例としては、Windows ランタイム型を基になる ABI の型に変換する-これは、オブジェクトに対する参照カウントのコントロールを行ったことを意味します。 この作業を行うには、 [ComPtr Class](../cpp/com-ptr-t-class.md) のスマート ポインターを使用することをお勧めします。 それ以外の場合、特にインターフェイスに対して Release を呼び出す必要があります。 次の例では、ref クラスを `IInspectable*`にキャストする方法を示します。

```cpp
#include <wrl.h>
using namespace Microsoft::WRL;
auto winRtObject = ref new SomeWinRTType();
ComPtr<IInspectable> inspectable = reinterpret_cast<IInspectable*>(winRtObject);
// ...
```

使用する場合**reinterpret_cast** oneWindows ランタイム インターフェイスからの変換を 2 回解放するオブジェクトが発生します。 そのため、のみを使用して、このキャスト Visual C 以外のコンポーネントの拡張機能インターフェイスに変換する場合。

## <a name="abi-types"></a>ABI の型

- ABI の型は、Windows SDK のヘッダーに置かれます。 判別しやすいように、ヘッダーは名前空間にちなんだ名前が付けられています ( `windows.storage.h`など)。

- ABI の型は、 `ABI::Windows::Storage::Streams::IBuffer*`のような特殊な ABI 名前空間に置かれます。

- Windows ランタイム インターフェイスの種類とその同等の ABI の型の間の変換は常に安全 — つまり`IBuffer^`に`ABI::IBuffer*`します。

- Windows ランタイムのランタイム クラスに常に変換する`IInspectable*`またはわかっている場合、既定のインターフェイス。

- ABI の型への変換後は、その型の有効期間を管理し、COM 規則に従う必要があります。 ABI のポインターの有効期間管理を容易にするために、 `WRL::ComPtr` を使用することをお勧めします。

次の表を安全に使用するケース**reinterpret_cast**します。 どの状況でも、キャストは両方向とも安全です。

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
