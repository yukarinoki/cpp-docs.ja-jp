---
description: '詳細情報: `__declspec`'
title: __declspec
ms.date: 03/21/2019
f1_keywords:
- __declspec_cpp
- __declspec
- _declspec
helpviewer_keywords:
- __declspec keyword [C++]
ms.openlocfilehash: 1a8644bc05319332967ffd7934e6799408c3d36d
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102465529"
---
# `__declspec`

**Microsoft 固有の仕様**

ストレージクラス情報を指定するための拡張属性構文では、キーワードを使用します **`__declspec`** 。これは、指定された型のインスタンスが、次に示す Microsoft 固有のストレージクラス属性を使用して格納されることを指定します。 その他のストレージクラス修飾子の例 **`static`** として、キーワードとキーワードがあり **`extern`** ます。 ただし、これらのキーワードは C および C++ 言語の ANSI 仕様の一部であるため、拡張属性構文では扱われません。 拡張属性構文は、Microsoft 固有の C および C++ 言語拡張を簡略化し、標準化します。

## <a name="grammar"></a>文法

*`decl-specifier`*:\
&emsp;**`__declspec (`**  *`extended-decl-modifier-seq`*  **`)`**

*`extended-decl-modifier-seq`*:\
&emsp; *`extended-decl-modifier`* <sub>opt</sub> \
&emsp;*`extended-decl-modifier`* *`extended-decl-modifier-seq`*

*`extended-decl-modifier`*:\
&emsp;**`align(`***番号***`)`**\
&emsp;**`allocate("`***segname***`")`**\
&emsp;**`allocator`**\
&emsp;**`appdomain`**\
&emsp;**`code_seg("`***segname***`")`**\
&emsp;**`deprecated`**\
&emsp;**`dllimport`**\
&emsp;**`dllexport`**\
&emsp;**`jitintrinsic`**\
&emsp;**`naked`**\
&emsp;**`noalias`**\
&emsp;**`noinline`**\
&emsp;**`noreturn`**\
&emsp;**`nothrow`**\
&emsp;**`novtable`**\
&emsp;**`no_sanitize_address`**\
&emsp;**`process`**\
&emsp;**`property(`**{ **`get=`** _get-func-name_ &#124; **`,put=`** _put-name_ }**`)`**\
&emsp;**`restrict`**\
&emsp;**`safebuffers`**\
&emsp;**`selectany`**\
&emsp;**`spectre(nomitigation)`**\
&emsp;**`thread`**\
&emsp;**`uuid("`***Comobjectguid***`")`**

空白は、宣言修飾子のシーケンスを区切ります。 その例は以降のセクションで示します。

拡張属性の文法では、Microsoft 固有のストレージクラス属性である、、、、、、、、、、、、、、、、、、、、、およびがサポートさ [`align`](../cpp/align-cpp.md) [`allocate`](../cpp/allocate.md) [`allocator`](../cpp/allocator.md) [`appdomain`](../cpp/appdomain.md) [`code_seg`](../cpp/code-seg-declspec.md) [`deprecated`](../cpp/deprecated-cpp.md) [`dllexport`](../cpp/dllexport-dllimport.md) [`dllimport`](../cpp/dllexport-dllimport.md) [`jitintrinsic`](../cpp/jitintrinsic.md) [`naked`](../cpp/naked-cpp.md) [`noalias`](../cpp/noalias.md) [`noinline`](../cpp/noinline.md) [`noreturn`](../cpp/noreturn.md) [`nothrow`](../cpp/nothrow-cpp.md) [`novtable`](../cpp/novtable.md) [`no_sanitize_address`](../cpp/no-sanitize-address.md) [`process`](../cpp/process.md) [`restrict`](../cpp/restrict.md) [`safebuffers`](../cpp/safebuffers.md) [`selectany`](../cpp/selectany.md) [`spectre`](../cpp/spectre.md) れてい [`thread`](../cpp/thread.md) ます。 また、これらの COM オブジェクト属性 (および) もサポートしてい [`property`](../cpp/property-cpp.md) [`uuid`](../cpp/uuid-cpp.md) ます。

、、、、、、、、、、、 **`code_seg`** **`dllexport`** **`dllimport`** およびの **`naked`** **`noalias`** **`nothrow`** **`no_sanitize_address`** **`property`** **`restrict`** **`selectany`** **`thread`** **`uuid`** 各ストレージクラス属性は、適用先のオブジェクトまたは関数の宣言のプロパティにすぎません。 属性は、 **`thread`** データとオブジェクトにのみ影響します。 **`naked`** 属性と **`spectre`** 属性は、関数にのみ影響します。 **`dllimport`** 属性と **`dllexport`** 属性は、関数、データ、およびオブジェクトに影響します。 **`property`**、、およびの各属性は、 **`selectany`** **`uuid`** COM オブジェクトに影響を与えます。

以前のバージョンとの互換性を維持するために、 **`_declspec`** **`__declspec`** コンパイラオプションの [ [ \( 言語拡張を無効にする](../build/reference/za-ze-disable-language-extensions.md) ] が指定されていない限り、はのシノニムになります。

キーワードは、 **`__declspec`** 単純な宣言の先頭に配置する必要があります。 コンパイラは警告なしで、 **`__declspec`** * または & の後に配置されたキーワードを無視し、宣言の変数識別子の前に配置します。

**`__declspec`** ユーザー定義型の宣言の先頭に指定された属性は、その型の変数に適用されます。 次に例を示します。

```cpp
__declspec(dllimport) class X {} varX;
```

この場合、属性は `varX` に適用されます。 **`__declspec`** またはキーワードの後に配置された属性は、 **`class`** **`struct`** ユーザー定義型に適用されます。 次に例を示します。

```cpp
class __declspec(dllimport) X {};
```

この場合、属性は `X` に適用されます。

単純な宣言に属性を使用するための一般的なガイドラインは次のとおり **`__declspec`** です。

*宣言子-seq* *init-宣言子リスト*。

*宣言指定子-seq* には、特に基本型 (、、、 **`int`** **`float`** **`typedef`** またはクラス名)、ストレージクラス (など **`static`** )、 **`extern`** または **`__declspec`** 拡張機能を含める必要があります。 *初期化子リスト* には、特に、宣言のポインター部分が含まれている必要があります。 次に例を示します。

```cpp
__declspec(selectany) int * pi1 = 0;   //Recommended, selectany & int both part of decl-specifier
int __declspec(selectany) * pi2 = 0;   //OK, selectany & int both part of decl-specifier
int * __declspec(selectany) pi3 = 0;   //ERROR, selectany is not part of a declarator
```

次のコードでは、整数型のスレッド ローカル変数を宣言して特定の値に初期化します。

```cpp
// Example of the __declspec keyword
__declspec( thread ) int tls_i = 1;
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[Keywords](../cpp/keywords-cpp.md)\
[C 拡張ストレージ クラス属性](../c-language/c-extended-storage-class-attributes.md)
