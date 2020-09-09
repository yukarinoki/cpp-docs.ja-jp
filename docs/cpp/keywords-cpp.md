---
title: C++ キーワード
description: C++ 標準言語キーワード、Microsoft 固有のキーワード、およびコンテキスト固有のキーワードの一覧を示します。
ms.custom: index-page
ms.date: 07/25/2020
helpviewer_keywords:
- keywords [C++]
ms.assetid: d7ca94a8-f785-41ce-9f73-d3c4fd508489
ms.openlocfilehash: 96fb4e6a51630f3b5297c6428297980b5c51ca36
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609148"
---
# <a name="keywords-c"></a>C++ キーワード

キーワードは、特別な意味を持つ定義済みおよび予約済みの識別子です。 プログラムで識別子として使用することはできません。 次のキーワードは Microsoft C++ 用に予約されています。 先頭にアンダースコアが付いていて、C++/CX および C++/CLI に指定された名前は Microsoft 拡張機能です。

## <a name="standard-c-keywords"></a>標準 C++ のキーワード

:::row:::
    :::column:::
        [`alignas`](align-cpp.md)\
        [`alignof`](alignof-operator.md)\
        [`and`](bitwise-and-operator-amp.md)<sup>b</sup>\
        [`and_eq`](assignment-operators.md)<sup>b</sup>\
        [`asm`](../assembler/inline/asm.md)<sup>a</sup>\
        [`auto`](auto-keyword.md)\
        [`bitand`](bitwise-and-operator-amp.md)<sup>b</sup>\
        [`bitor`](bitwise-inclusive-or-operator-pipe.md)<sup>b</sup>\
        [`bool`](bool-cpp.md)\
        [`break`](break-statement-cpp.md)\
        [`case`](switch-statement-cpp.md)\
        [`catch`](try-throw-and-catch-statements-cpp.md)\
        [`char`](fundamental-types-cpp.md)\
        [`char8_t`](fundamental-types-cpp.md)<sup>c</sup>\
        [`char16_t`](char-wchar-t-char16-t-char32-t.md)\
        [`char32_t`](char-wchar-t-char16-t-char32-t.md)\
        [`class`](class-cpp.md)\
        [`compl`](one-s-complement-operator-tilde.md)<sup>b</sup>\
        **`concept`**<sup>c</sup>\
        [`const`](const-cpp.md)\
        [`const_cast`](const-cast-operator.md)\
        **`consteval`**<sup>c</sup>\
        [`constexpr`](constexpr-cpp.md)
    :::column-end:::
    :::column:::
        **`constinit`**<sup>c</sup>\
        [`continue`](continue-statement-cpp.md)\
        **`co_await`**<sup>c</sup>\
        **`co_return`**<sup>c</sup>\
        **`co_yield`**<sup>c</sup>\
        [`decltype`](decltype-cpp.md)\
        [`default`](switch-statement-cpp.md)\
        [`delete`](delete-operator-cpp.md)\
        [`do`](do-while-statement-cpp.md)\
        [`double`](fundamental-types-cpp.md)\
        [`dynamic_cast`](dynamic-cast-operator.md)\
        [`else`](if-else-statement-cpp.md)\
        [`enum`](enumerations-cpp.md)\
        [`explicit`](user-defined-type-conversions-cpp.md)\
        **`export`**<sup>c</sup>\
        [`extern`](using-extern-to-specify-linkage.md)\
        [`false`](false-cpp.md)\
        [`float`](fundamental-types-cpp.md)\
        [`for`](for-statement-cpp.md)\
        [`friend`](friend-cpp.md)\
        [`goto`](goto-statement-cpp.md)\
        [`if`](if-else-statement-cpp.md)\
        [`inline`](inline-functions-cpp.md)
    :::column-end:::
    :::column:::
        [`int`](fundamental-types-cpp.md)\
        [`long`](fundamental-types-cpp.md)\
        [`mutable`](mutable-data-members-cpp.md)\
        [`namespace`](namespaces-cpp.md)\
        [`new`](new-operator-cpp.md)\
        [`noexcept`](noexcept-cpp.md)\
        [`not`](logical-negation-operator-exclpt.md)<sup>b</sup>\
        [`not_eq`](equality-operators-equal-equal-and-exclpt-equal.md)<sup>b</sup>\
        [`nullptr`](nullptr.md)\
        [`operator`](operator-overloading.md)\
        [`or`](logical-or-operator-pipe-pipe.md)<sup>b</sup>\
        [`or_eq`](assignment-operators.md)<sup>b</sup>\
        [`private`](private-cpp.md)\
        [`protected`](protected-cpp.md)\
        [`public`](public-cpp.md)\
        [`register`](storage-classes-cpp.md#register) [`reinterpret_cast`](reinterpret-cast-operator.md)\
        **`requires`**<sup>c</sup>\
        [`return`](return-statement-cpp.md)\
        [`short`](fundamental-types-cpp.md)\
        [`signed`](fundamental-types-cpp.md)\
        [`sizeof`](sizeof-operator.md)\
        [`static`](storage-classes-cpp.md)\
        [`static_assert`](static-assert.md)
    :::column-end:::
    :::column:::
        [`static_cast`](static-cast-operator.md)\
        [`struct`](struct-cpp.md)\
        [`switch`](switch-statement-cpp.md)\
        [`template`](templates-cpp.md)\
        [`this`](this-pointer.md)\
        [`thread_local`](storage-classes-cpp.md#thread_local)\
        [`throw`](try-throw-and-catch-statements-cpp.md)\
        [`true`](true-cpp.md)\
        [`try`](try-throw-and-catch-statements-cpp.md)\
        [`typedef`](aliases-and-typedefs-cpp.md)\
        [`typeid`](typeid-operator.md)\
        [`typename`](typename.md)\
        [`union`](unions.md)\
        [`unsigned`](fundamental-types-cpp.md)\
        [`using`](using-declaration.md) 定義
        [`using`](namespaces-cpp.md#using_directives) 指示
        [`virtual`](virtual-cpp.md)\
        [`void`](void-cpp.md)\
        [`volatile`](volatile-cpp.md)\
        [`wchar_t`](fundamental-types-cpp.md)\
        [`while`](while-statement-cpp.md)\
        [`xor`](bitwise-exclusive-or-operator-hat.md)<sup>b</sup>\
        [`xor_eq`](assignment-operators.md)<sup>b</sup>
    :::column-end:::
:::row-end:::

Microsoft 固有のキーワード<sup>を指定すると</sup>、 **`__asm`** C++ の構文が置き換えら **`asm`** れます。 **`asm`** は、他の C++ 実装との互換性のために予約されていますが、実装されていません。 **`__asm`** X86 ターゲットでインラインアセンブリに使用します。 Microsoft C++ では、他のターゲットのインラインアセンブリはサポートされていません。

<sup>b</sup>拡張演算子のシノニムは、 [`/permissive-`](../build/reference/permissive-standards-conformance.md) [ `/Za` \( 言語拡張を無効](../build/reference/za-ze-disable-language-extensions.md)にしたときのキーワードです。 Microsoft 拡張機能が有効になっている場合、キーワードはキーワードではありません。

<sup>c</sup> [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) は、が指定されている場合にサポートされます。

## <a name="microsoft-specific-c-keywords"></a>Microsoft 固有の C++ キーワード

C++ では、2つの連続するアンダースコアを含む識別子は、コンパイラの実装用に予約されています。 Microsoft の規約では、Microsoft 固有のキーワードの前に2つのアンダースコアが付いています。 これらの単語を識別子名として使用することはできません。

Microsoft 拡張機能は既定で有効になっています。 プログラムが完全に移植可能であることを確認するに [`/permissive-`](../build/reference/permissive-standards-conformance.md) は、コンパイル時に [ [ `/Za` \( 言語拡張機能の無効化](../build/reference/za-ze-disable-language-extensions.md)] オプションを指定して Microsoft 拡張機能を無効にすることができます。 これらのオプションでは、一部の Microsoft 固有のキーワードが無効になります。

Microsoft 拡張機能を有効にすると、Microsoft 固有のキーワードをプログラム内で使用できます。 ANSI 準拠のために、これらのキーワードは 2 つのアンダースコアで始まります。 旧バージョンとの互換性のために、多くの下線付きキーワードの1つのアンダースコアバージョンがサポートされています。 **`__cdecl`** キーワードは、先頭にアンダースコアがない場合に使用できます。

**`__asm`** キーワードは C++ の構文に代わるもの **`asm`** です。 **`asm`** は、他の C++ 実装との互換性のために予約されていますが、実装されていません。 **`__asm`** を使用します。

キーワードの使用は、 **`__based`** 32 ビットおよび64ビットのターゲットコンパイルの場合に限られます。

:::row:::
    :::column:::
        [`__alignof`](alignof-operator.md)<sup>e</sup>\
        [`__asm`](../assembler/inline/asm.md)<sup>e</sup>\
        [`__assume`](../intrinsics/assume.md)<sup>e</sup>\
        [`__based`](based-pointers-cpp.md)<sup>e</sup>\
        [`__cdecl`](cdecl.md)<sup>e</sup>\
        [`__declspec`](declspec.md)<sup>e</sup>\
        [`__event`](event.md)\
        [`__except`](try-except-statement.md)<sup>e</sup>\
        [`__fastcall`](fastcall.md)<sup>e</sup>\
        [`__finally`](try-finally-statement.md)<sup>e</sup>\
        [`__forceinline`](inline-functions-cpp.md)<sup>e</sup>
    :::column-end:::
    :::column:::
        [`__hook`](hook.md)<sup>d</sup>\
        [`__if_exists`](if-exists-statement.md)\
        [`__if_not_exists`](if-not-exists-statement.md)\
        [`__inline`](inline-functions-cpp.md)<sup>e</sup>\
        [`__int16`](int8-int16-int32-int64.md)<sup>e</sup>\
        [`__int32`](int8-int16-int32-int64.md)<sup>e</sup>\
        [`__int64`](int8-int16-int32-int64.md)<sup>e</sup>\
        [`__int8`](int8-int16-int32-int64.md)<sup>e</sup>\
        [`__interface`](interface.md)\
        [`__leave`](try-finally-statement.md)<sup>e</sup>\
        [`__m128`](m128.md)
    :::column-end:::
    :::column:::
        [`__m128d`](m128d.md)\
        [`__m128i`](m128i.md)\
        [`__m64`](m64.md)\
        [`__multiple_inheritance`](inheritance-keywords.md)<sup>e</sup>\
        [`__ptr32`](ptr32-ptr64.md)<sup>e</sup>\
        [`__ptr64`](ptr32-ptr64.md)<sup>つまり</sup>\
        [`__raise`](raise.md)\
        [`__restrict`](extension-restrict.md)<sup>e</sup>\
        [`__single_inheritance`](inheritance-keywords.md)<sup>つまり</sup>\
        [`__sptr`](sptr-uptr.md)<sup>つまり</sup>\
        [`__stdcall`](stdcall.md)<sup>e</sup>
    :::column-end:::
    :::column:::
        [`__super`](super.md)\
        [`__thiscall`](thiscall.md)\
        [`__unaligned`](unaligned.md)<sup>e</sup>\
        [`__unhook`](unhook.md)<sup>d</sup>\
        [`__uptr`](sptr-uptr.md)<sup>e</sup>\
        [`__uuidof`](uuidof-operator.md)<sup>e</sup>\
        [`__vectorcall`](vectorcall.md)<sup>e</sup>\
        [`__virtual_inheritance`](inheritance-keywords.md)<sup>e</sup>\
        [`__w64`](w64.md)<sup>e</sup>\
        [`__wchar_t`](fundamental-types-cpp.md)
    :::column-end:::
:::row-end:::

イベント処理で使用される<sup>d</sup>組み込み関数。

<sup>e</sup> 以前のバージョンとの下位互換性を維持するために、これらのキーワードは、Microsoft 拡張機能が有効になっている場合 (既定)、2つの先頭のアンダースコアと1つの先頭にアンダースコアが使用されます。

## <a name="microsoft-keywords-in-__declspec-modifiers"></a>__Declspec 修飾子内の Microsoft キーワード

これらの識別子は、修飾子の拡張属性です **`__declspec`** 。 これらは、そのコンテキスト内のキーワードと見なされます。

:::row:::
    :::column:::
        [`align`](align-cpp.md)\
        [`allocate`](allocate.md)\
        [`allocator`](allocator.md)\
        [`appdomain`](appdomain.md)\
        [`code_seg`](code-seg-declspec.md)\
        [`deprecated`](deprecated-cpp.md)
    :::column-end:::
    :::column:::
        [`dllexport`](dllexport-dllimport.md)\
        [`dllimport`](dllexport-dllimport.md)\
        [`jitintrinsic`](jitintrinsic.md)\
        [`naked`](naked-cpp.md)\
        [`noalias`](noalias.md)\
        [`noinline`](noinline.md)
    :::column-end:::
    :::column:::
        [`noreturn`](noreturn.md)\
        [`nothrow`](nothrow-cpp.md)\
        [`novtable`](novtable.md)\
        [`process`](process.md)\
        [`property`](property-cpp.md)\
        [`restrict`](restrict.md)
    :::column-end:::
    :::column:::
        [`safebuffers`](safebuffers.md)\
        [`selectany`](selectany.md)\
        [`spectre`](spectre.md)\
        [`thread`](thread.md)\
        [`uuid`](uuid-cpp.md)
    :::column-end:::
:::row-end:::

## <a name="ccli-and-ccx-keywords"></a>C++/CLI および C++/CX キーワード

:::row:::
    :::column:::
        [`__abstract`](../dotnet/declaration-of-a-managed-class-type.md)<sup>f</sup>\
        [`__box`](../dotnet/value-type-semantics.md)<sup>f</sup>\
        [`__delegate`](../dotnet/delegates-and-events.md)<sup>f</sup>\
        [`__gc`](../dotnet/declaration-of-a-clr-reference-class-object.md)<sup>f</sup>\
        [`__identifier`](../extensions/identifier-cpp-cli.md)\
        [`__nogc`](../dotnet/declaration-of-a-clr-reference-class-object.md)<sup>f</sup>\
        [`__noop`](../intrinsics/noop.md)\
        **`__pin`**<sup>f</sup>\
        **`__property`**<sup>f</sup>\
        **`__sealed`**<sup>f</sup>
    :::column-end:::
    :::column:::
        [`__try_cast`](../dotnet/cast-notation-and-introduction-of-safe-cast-angles.md)<sup>f</sup>\
        [`__value`](../dotnet/value-type-semantics.md)<sup>f</sup>\
        [`abstract`](../extensions/abstract-cpp-component-extensions.md)<sup>g</sup>\
        [`array`](../extensions/arrays-cpp-component-extensions.md)<sup>g</sup>\
        [`as_friend`](../preprocessor/hash-using-directive-cpp.md)\
        [`delegate`](../extensions/delegate-cpp-component-extensions.md)<sup>g</sup>\
        [`enum class`](../extensions/enum-class-cpp-component-extensions.md)\
        [`enum struct`](../extensions/enum-class-cpp-component-extensions.md)\
        [`event`](../extensions/event-cpp-component-extensions.md)<sup>g</sup>
    :::column-end:::
    :::column:::
        [`finally`](../dotnet/finally.md)\
        [`for each in`](../dotnet/for-each-in.md)\
        [`gcnew`](../extensions/ref-new-gcnew-cpp-component-extensions.md)<sup>g</sup>\
        [`generic`](../extensions/generics-cpp-component-extensions.md)<sup>g</sup>\
        [`initonly`](../dotnet/initonly-cpp-cli.md)\
        [`interface class`](../extensions/interface-class-cpp-component-extensions.md)<sup>g</sup>\
        [`interface struct`](../extensions/interface-class-cpp-component-extensions.md)<sup>g</sup>\
        [`interior_ptr`](../extensions/interior-ptr-cpp-cli.md)<sup>g</sup>\
        [`literal`](../extensions/literal-cpp-component-extensions.md)<sup>g</sup>
    :::column-end:::
    :::column:::
        [`new`](../extensions/new-new-slot-in-vtable-cpp-component-extensions.md)<sup>g</sup>\
        [`property`](../extensions/property-cpp-component-extensions.md)<sup>g</sup>\
        [`ref class`](../extensions/classes-and-structs-cpp-component-extensions.md)\
        [`ref struct`](../extensions/classes-and-structs-cpp-component-extensions.md)\
        [`safecast`](../extensions/safe-cast-cpp-component-extensions.md)\
        [`sealed`](../extensions/sealed-cpp-component-extensions.md)<sup>g</sup>\
        [`typeid`](../extensions/typeid-cpp-component-extensions.md)\
        [`value class`](../extensions/classes-and-structs-cpp-component-extensions.md)<sup>g</sup>\
        [`value struct`](../extensions/classes-and-structs-cpp-component-extensions.md)<sup>g</sup>
    :::column-end:::
:::row-end:::

<sup>f</sup> Managed Extensions for C++ にのみ適用されます。 この構文は現在非推奨とされます。 詳細については、「[Component Extensions for Runtime Platforms](../extensions/component-extensions-for-runtime-platforms.md)」を参照してください。

C++/CLI に適用される<sup>g</sup>

## <a name="see-also"></a>関連項目

[構文規則](lexical-conventions.md)<br/>
[C++ の組み込み演算子、優先順位、および結合規則](cpp-built-in-operators-precedence-and-associativity.md)
