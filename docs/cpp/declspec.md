---
title: __declspec
ms.date: 03/21/2019
f1_keywords:
- __declspec_cpp
- __declspec
- _declspec
helpviewer_keywords:
- __declspec keyword [C++]
ms.openlocfilehash: e0c99ea9379aa6e29096250e8bd36ce3d4f183e8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180226"
---
# <a name="__declspec"></a>__declspec

**Microsoft 固有の仕様**

ストレージクラス情報を指定するための拡張属性構文では、 **__declspec**キーワードを使用します。これは、指定された型のインスタンスが、次に示す Microsoft 固有のストレージクラス属性を使用して格納されることを指定します。 その他のストレージクラス修飾子の例としては、 **static**および**extern**キーワードがあります。 ただし、これらのキーワードは C および C++ 言語の ANSI 仕様の一部であるため、拡張属性構文では扱われません。 拡張属性構文は、Microsoft 固有の C および C++ 言語拡張を簡略化し、標準化します。

## <a name="grammar"></a>文法

*宣言子*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__declspec (** *拡張宣言-seq* **)**

*extended-decl-modifier-seq*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*extended-decl-modifier*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*拡張*宣言修飾子の*シーケンス*です。

*extended-decl-modifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**アライン (** *#* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**割り当て ("** *segname* **")**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**アロケーター**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**appdomain**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**code_seg ("** *segname* **")**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**非推奨**となりました<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**jitintrinsic**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**naked**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**noalias**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**noinline**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**noreturn**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**nothrow**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**novtable**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**プロセス**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**プロパティ (** { **get =** _get_func_name_ &#124; **, put =** _put_func_name_ } **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**制限**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**safebuffers**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**selectany**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**spectre (nomitigation)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**thread**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**uuid ("** *comobjectguid* **")**

空白は、宣言修飾子のシーケンスを区切ります。 その例は以降のセクションで示します。

拡張属性の文法は、次の Microsoft 固有のストレージクラス属性をサポートしています: [align](../cpp/align-cpp.md)、 [allocate](../cpp/allocate.md)、[アロケーター](../cpp/allocator.md)、 [appdomain](../cpp/appdomain.md)、 [code_seg](../cpp/code-seg-declspec.md)、 [naked](../cpp/naked-cpp.md)[非推奨](../cpp/deprecated-cpp.md)、 [dllexport](../cpp/dllexport-dllimport.md)、 [dllimport](../cpp/dllexport-dllimport.md)、 [jitintrinsic](../cpp/jitintrinsic.md)、 [noalias](../cpp/noalias.md)、 [noinline](../cpp/noinline.md)、 [noreturn](../cpp/noreturn.md)、 [nothrow](../cpp/nothrow-cpp.md)、 [novtable](../cpp/novtable.md)、 [process](../cpp/process.md)、 [restrict](../cpp/restrict.md)、 [safebuffers](../cpp/safebuffers.md)、 [selectany](../cpp/selectany.md)、 [spectre](../cpp/spectre.md)、 [thread](../cpp/thread.md)。 また、これらの COM オブジェクト属性である[プロパティ](../cpp/property-cpp.md)と[uuid](../cpp/uuid-cpp.md)もサポートしています。

**Code_seg**、 **dllexport**、 **dllimport**、noalias **、** **nothrow**、 **property**、 **restrict**、 **selectany**、 **noalias** **thread**、および**uuid**の各ストレージクラス属性は、適用先のオブジェクトまたは関数の宣言のプロパティにすぎません。 **Thread**属性は、データとオブジェクトにのみ影響します。 Spectre 属性と**spectre** **属性は、** 関数にのみ影響します。 **Dllimport**属性と**dllexport**属性は、関数、データ、およびオブジェクトに影響します。 **プロパティ**、 **selectany**、および**uuid**属性は COM オブジェクトに影響を与えます。

以前のバージョンとの互換性のために、コンパイラオプション[/za \(無効になっている言語拡張)](../build/reference/za-ze-disable-language-extensions.md)が指定されていない場合、 **_declspec**は **__declspec**のシノニムになります。

**__Declspec**キーワードは、単純な宣言の先頭に配置する必要があります。 コンパイラは、警告なしで、* または & の後に配置された **__declspec**キーワードを無視し、宣言の変数識別子の前に配置します。

ユーザー定義型の宣言の先頭に指定された **__declspec**属性は、その型の変数に適用されます。 次に例を示します。

```cpp
__declspec(dllimport) class X {} varX;
```

この場合、属性は `varX` に適用されます。 **クラス**または**struct**キーワードの後に配置された **__declspec**属性は、ユーザー定義型に適用されます。 次に例を示します。

```cpp
class __declspec(dllimport) X {};
```

この場合、属性は `X` に適用されます。

単純な宣言に **__declspec**属性を使用するための一般的なガイドラインは次のとおりです。

*宣言子-seq* *init-宣言子リスト*。

*宣言指定子-seq*には、特に基本型 ( **int**、 **float**、 **typedef**、またはクラス名)、ストレージクラス ( **static**、 **extern**など)、または **__declspec**拡張機能が含まれている必要があります。 *初期化子リスト*には、特に、宣言のポインター部分が含まれている必要があります。 次に例を示します。

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

## <a name="see-also"></a>参照

[キーワード](../cpp/keywords-cpp.md)<br/>
[C 拡張ストレージ クラス属性](../c-language/c-extended-storage-class-attributes.md)
