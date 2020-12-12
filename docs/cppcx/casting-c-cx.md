---
description: '詳細情報: キャスト (C++/CX)'
title: キャスト (C++/CX)
ms.date: 06/19/2018
ms.assetid: 5247f6c7-6a0a-4021-97c9-21c868bd9455
ms.openlocfilehash: 90b9e90833acc14bcf76287b44f70fb914c7604a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190277"
---
# <a name="casting-ccx"></a>キャスト (C++/CX)

4つの異なるキャスト演算子は Windows ランタイム型 ( [Static_cast operator](../cpp/static-cast-operator.md)、 [dynamic_cast Operator](../cpp/dynamic-cast-operator.md)、 **Safe_cast operator**、および [reinterpret_cast operator](../cpp/reinterpret-cast-operator.md)) に適用されます。 変換を **`static_cast`** 実行できない場合は、safe_cast して例外をスローします。[Static_cast 演算子](../cpp/static-cast-operator.md)は、コンパイル時の型チェックも実行します。 **`dynamic_cast`****`nullptr`** 型の変換に失敗した場合はを返します。 は **`reinterpret_cast`** null 以外の値を返しますが、無効である可能性があります。 このため、 **`reinterpret_cast`** キャストが成功することがわかっている場合を除き、を使用しないことをお勧めします。 また、C++/CX コードはと同じであるため、C スタイルのキャストは使用しないことをお勧め **`reinterpret_cast`** します。

コンパイラとランタイムは、暗黙的なキャストも実行します。たとえば、ボックス化操作で、パラメーターの型が `Object^`であるメソッドに値型または組み込み型が引数として渡される場合です。 理論的には、暗黙的なキャストは実行時に例外を引き起こしません。コンパイラが暗黙的な変換を実行できない場合は、コンパイル時にエラーが発生します。

Windows ランタイムは COM に対する抽象化であり、例外の代わりに HRESULT エラーコードを使用します。 一般に、 [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) は E_NOINTERFACE の低レベルの COM エラーを表します。

## <a name="static_cast"></a>static_cast

**`static_cast`** コンパイル時にをチェックして、2つの型の間に継承関係があるかどうかを確認します。 2 つの型に継承関係がない場合は、キャストによってコンパイラ エラーが発生します。

Ref クラスのを使用すると、 **`static_cast`** 実行時チェックも実行されます。 **`static_cast`** Ref クラスのは、コンパイル時に検証を渡すことができますが、実行時には失敗します。この場合、 `Platform::InvalidCastException` がスローされます。 一般的に、このような例外を処理する必要はありません。ほとんどの例外は常に、開発時およびテスト時に解決できるプログラミング エラーを示しているためです。

**`static_cast`** この2つの型の間のリレーションシップをコードが明示的に宣言する場合は、キャストが確実に機能するようにします。

```cpp
    interface class A{};
    public ref class Class1 sealed : A { };
    // ...
    A^ obj = ref new Class1(); // Class1 is an A
    // You know obj is a Class1. The compiler verifies that this is possible, and in C++/CX a run-time check is also performed.
    Class1^ c = static_cast<Class1^>(obj);
```

## <a name="safe_cast"></a>safe_cast

**Safe_cast** 演算子は Windows ランタイムの一部です。 変換が失敗すると、実行時の型チェックを実行して `Platform::InvalidCastException` をスローします。 実行時エラーが例外的な条件を示している場合は、 **safe_cast** を使用します。 **Safe_cast** の主な目的は、開発フェーズおよびテストフェーズで発生した時点でのプログラミングエラーを特定するのに役立ちます。 ハンドルされていない例外自体がエラーの位置を示しているため、例外を処理する必要はありません。

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

## <a name="dynamic_cast"></a>dynamic_cast

を使用すると **`dynamic_cast`** 、より多くの派生型にオブジェクト (具体的には hat) をキャストするときに、ターゲットオブジェクトがである場合や、キャストが失敗する可能性があり、 **^** **`nullptr`** その条件を例外ではなく通常のコードパスとして処理することが予想されます。 たとえば、[空の **アプリ (ユニバーサル Windows)** ] プロジェクトテンプレートでは、を使用して、 `OnLaunched` **`dynamic_cast`** アプリウィンドウにコンテンツがあるかどうかをテストします。 コンテンツが含まれていなくても、エラーではありません。これは予期された状態です。 `Windows::Current::Content` は `Windows::UI::XAML::UIElement` であり、継承階層内のより強い派生型である `Windows::UI.XAML::Controls::Frame`への変換が実行されます。

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

のもう1つの用途 **`dynamic_cast`** は、ボックス化された `Object^` 値型が含まれているかどうかを判断するために、をプローブすることです。 この場合、 `dynamic_cast<Platform::Box>` または `dynamic_cast<Platform::IBox>`を試行します。

## <a name="dynamic_cast-and-tracking-references-"></a>dynamic_cast と追跡参照 (%) 

を追跡参照に適用することもでき **`dynamic_cast`** ますが、この場合、キャストは **safe_cast** のように動作します。 `Platform::InvalidCastException`追跡参照の値をにすることはできないため、エラーが発生した場合はをスロー **`nullptr`** します。

## <a name="reinterpret_cast"></a>reinterpret_cast

[reinterpret_cast](../cpp/reinterpret-cast-operator.md) を使用しないことをお勧めします。コンパイル時のチェックと、ランタイム チェックのどちらも実行されないためです。 最悪のケースでは、を使用する **`reinterpret_cast`** と、開発時にプログラミングエラーが検出されず、プログラムの動作で軽度または致命的なエラーが発生する可能性があります。 したがって、関係のない **`reinterpret_cast`** 型間でキャストする必要があり、キャストが成功することがわかっている場合にのみ、このようなまれなケースでのみを使用することをお勧めします。 まれに使用される例として、Windows ランタイムの型を基になる ABI の型に変換することが挙げられます。これは、オブジェクトの参照カウントを制御することを意味します。 この作業を行うには、 [ComPtr Class](../cpp/com-ptr-t-class.md) のスマート ポインターを使用することをお勧めします。 それ以外の場合、特にインターフェイスに対して Release を呼び出す必要があります。 次の例では、ref クラスを `IInspectable*`にキャストする方法を示します。

```cpp
#include <wrl.h>
using namespace Microsoft::WRL;
auto winRtObject = ref new SomeWinRTType();
ComPtr<IInspectable> inspectable = reinterpret_cast<IInspectable*>(winRtObject);
// ...
```

を使用し **`reinterpret_cast`** て oneWindows ランタイムインターフェイスから別のランタイムインターフェイスに変換すると、オブジェクトが2回解放されます。 したがって、このキャストは、C + + コンポーネント拡張インターフェイスに変換する場合にのみ使用してください。

## <a name="abi-types"></a>ABI の型

- ABI の型は、Windows SDK のヘッダーに置かれます。 判別しやすいように、ヘッダーは名前空間にちなんだ名前が付けられています ( `windows.storage.h`など)。

- ABI の型は、 `ABI::Windows::Storage::Streams::IBuffer*`のような特殊な ABI 名前空間に置かれます。

- Windows ランタイムインターフェイス型とそれに対応する ABI 型の間の変換は、常に安全です (つまり、) `IBuffer^` `ABI::IBuffer*` 。

- Windows ランタイムランタイムクラスは、常に、 `IInspectable*` またはその既定のインターフェイス (既知の場合) に変換する必要があります。

- ABI の型への変換後は、その型の有効期間を管理し、COM 規則に従う必要があります。 ABI のポインターの有効期間管理を容易にするために、 `WRL::ComPtr` を使用することをお勧めします。

次の表は、を使用しても安全なケースをまとめたもの **`reinterpret_cast`** です。 どの状況でも、キャストは両方向とも安全です。

| キャスト元、キャスト先 | キャスト、キャスト、 |
|--|--|
| `HSTRING` | `String^` |
| `HSTRING*` | `String^*` |
| `IInspectable*` | `Object^` |
| `IInspectable**` | `Object^*` |
| `IInspectable-derived-type*` | `same-interface-from-winmd^` |
| `IInspectable-derived-type**` | `same-interface-from-winmd^*` |
| `IDefault-interface-of-RuntimeClass*` | `same-RefClass-from-winmd^` |
| `IDefault-interface-of-RuntimeClass**` | `same-RefClass-from-winmd^*` |

## <a name="see-also"></a>関連項目

- [型システム](../cppcx/type-system-c-cx.md)
- [C++/CX 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)
- [名前空間のリファレンス](../cppcx/namespaces-reference-c-cx.md)
