---
title: _ _declspec |Microsoft Docs
ms.custom: ''
ms.date: 1/23/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __declspec_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++]
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4358712e5573095229a48a6d08b78706c608874d
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403649"
---
# <a name="declspec"></a>__declspec

**Microsoft 固有の仕様**

ストレージ クラス情報の使用方法を指定するための拡張属性構文、 **_ _declspec**キーワードで、指定された型のインスタンスが以下に示す Microsoft 固有ストレージ クラス属性に保存することを指定します。 その他のストレージ クラス修飾子の例、**静的**と**extern**キーワード。 ただし、これらのキーワードは C および C++ 言語の ANSI 仕様の一部であるため、拡張属性構文では扱われません。 拡張属性構文は、Microsoft 固有の C および C++ 言語拡張を簡略化し、標準化します。

## <a name="grammar"></a>文法

*decl-specifier*:  
&nbsp;&nbsp;&nbsp;&nbsp;**_ _declspec (***拡張修飾子宣言 seq***)** 

*extended-decl-modifier-seq*:  
&nbsp;&nbsp;&nbsp;&nbsp;*拡張宣言修飾子*<sub>選択</sub>  
&nbsp;&nbsp;&nbsp;&nbsp;*拡張宣言修飾子**拡張修飾子宣言 seq*

*extended-decl-modifier*:  
&nbsp;&nbsp;&nbsp;&nbsp;**align(** *#* **)**  
&nbsp;&nbsp;&nbsp;&nbsp;**allocate("** *segname* **")**  
&nbsp;&nbsp;&nbsp;&nbsp;**appdomain**  
&nbsp;&nbsp;&nbsp;&nbsp;**code_seg("** *segname* **")**  
&nbsp;&nbsp;&nbsp;&nbsp;**非推奨とされます。**  
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**  
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**  
&nbsp;&nbsp;&nbsp;&nbsp;**jitintrinsic**  
&nbsp;&nbsp;&nbsp;&nbsp;**naked**  
&nbsp;&nbsp;&nbsp;&nbsp;**noalias**  
&nbsp;&nbsp;&nbsp;&nbsp;**noinline**  
&nbsp;&nbsp;&nbsp;&nbsp;**noreturn**  
&nbsp;&nbsp;&nbsp;&nbsp;**nothrow**  
&nbsp;&nbsp;&nbsp;&nbsp;**novtable**  
&nbsp;&nbsp;&nbsp;&nbsp;**プロセス**  
&nbsp;&nbsp;&nbsp;&nbsp;**property(** { **get=**_get_func_name_ &#124; **,put=**_put_func_name_ } **)**  
&nbsp;&nbsp;&nbsp;&nbsp;**restrict**  
&nbsp;&nbsp;&nbsp;&nbsp;**safebuffers**  
&nbsp;&nbsp;&nbsp;&nbsp;**selectany**  
&nbsp;&nbsp;&nbsp;&nbsp;**spectre(nomitigation)**  
&nbsp;&nbsp;&nbsp;&nbsp;**スレッド**  
&nbsp;&nbsp;&nbsp;&nbsp;**uuid("** *ComObjectGUID* **")**  

空白は、宣言修飾子のシーケンスを区切ります。 その例は以降のセクションで示します。

文法の拡張属性は、これらの Microsoft 固有ストレージ クラス属性をサポートしています: [align](../cpp/align-cpp.md)、[割り当てる](../cpp/allocate.md)、 [appdomain](../cpp/appdomain.md)、 [code_seg](../cpp/code-seg-declspec.md)、[非推奨とされます](../cpp/deprecated-cpp.md)、 [dllexport](../cpp/dllexport-dllimport.md)、 [dllimport](../cpp/dllexport-dllimport.md)、 [jitintrinsic](../cpp/jitintrinsic.md)、 [naked](../cpp/naked-cpp.md)、 [noalias](../cpp/noalias.md)、 [noinline](../cpp/noinline.md)、 [noreturn](../cpp/noreturn.md)、 [nothrow](../cpp/nothrow-cpp.md)、 [novtable](../cpp/novtable.md)、[プロセス](../cpp/process.md)、[制限](../cpp/restrict.md)、 [safebuffers](../cpp/safebuffers.md)、 [selectany](../cpp/selectany.md)、 [spectre](../cpp/spectre.md)、と[スレッド](../cpp/thread.md)します。 これらの COM オブジェクトの属性もサポートしています:[プロパティ](../cpp/property-cpp.md)と[uuid](../cpp/uuid-cpp.md)します。

**Code_seg**、 **dllexport**、 **dllimport**、 **naked**、 **noalias**、 **nothrow**、**プロパティ**、**制限**、 **selectany**、**スレッド**、および**uuid**ストレージ クラス属性は、オブジェクトまたは関数を適用する対象の宣言のみのプロパティ。 **スレッド**属性は、データに影響し、オブジェクトのみです。 **Naked**と**spectre**属性は関数だけに影響します。 **Dllimport**と**dllexport**属性は、関数、データ、およびオブジェクトに影響します。 **プロパティ**、 **selectany**、および**uuid**属性は COM オブジェクトに影響します。

**_ _Declspec**キーワードは、単純な宣言の先頭に配置する必要があります。 警告、なし、コンパイラは無視 **_ _declspec**キーワードの後に配置 * または (& a) と宣言で変数の識別子の前にします。

A **_ _declspec**その型の変数にユーザー定義型の宣言の先頭で指定された属性が適用されます。 例えば:

```cpp
__declspec(dllimport) class X {} varX;
```

この場合、属性は `varX` に適用されます。 A **_ _declspec**属性に配置した後、**クラス**または**構造体**キーワードは、ユーザー定義型に適用されます。 例えば:

```cpp
class __declspec(dllimport) X {};
```

この場合、属性は `X` に適用されます。

使用するための一般的なガイドライン、 **_ _declspec**単純な宣言子の属性を次に示します。

*decl-specifier-seq* *init-declarator-list*;

*宣言-seq 指定子*含める必要があります、特に、基本データ型 (例: **int**、 **float**、 **typedef**、またはクラス名)、ストレージ クラス (例:**静的**、 **extern**)、または **_ _declspec**拡張機能。 *Init 宣言リスト*含める必要があります、その際、ポインター宣言の一部です。 例えば:

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
 [キーワード](../cpp/keywords-cpp.md)  
 [C 拡張ストレージ クラス属性](../c-language/c-extended-storage-class-attributes.md)  