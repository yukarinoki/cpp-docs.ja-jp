---
description: pragmaMicrosoft C/c + + での section ディレクティブの詳細について説明します。
title: 下 pragma
ms.date: 01/22/2021
f1_keywords:
- section_CPP
- vc-pragma.section
helpviewer_keywords:
- pragma, section
- section pragma
no-loc:
- pragma
ms.openlocfilehash: 8bd55bbba65480b7345376059489d8aef945ab34
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713234"
---
# <a name="section-no-locpragma"></a>`section` pragma

OBJ ファイルにセクションを作成します。

## <a name="syntax"></a>構文

> **`#pragma section( "`***セクション-名前* **`"`**[ **`,`** *属性*]**`)`**

## <a name="remarks"></a>解説

この記事では、 *セグメント* と *セクション* という用語は同じ意味を持ちます。

セクションが定義されると、残りのコンパイルのために有効なままになります。 ただし、を使用する必要があり [`__declspec(allocate)`](../cpp/allocate.md) ます。または、セクションに何も配置されません。

*section-name* は、セクションの名前になる必須パラメーターです。 標準セクション名と競合する名前は付けられません。 [`/SECTION`](../build/reference/section-specify-section-attributes.md)セクションを作成するときに使用しない名前の一覧については、「」を参照してください。

*attributes* は、セクションに割り当てる1つ以上のコンマ区切りの属性で構成される省略可能なパラメーターです。 使用できる *属性* は次のとおりです。

| 属性 | 説明 |
|--|--|
| **`read`** | データの読み取り操作を有効にします。 |
| **`write`** | データの書き込み操作を有効にします。 |
| **`execute`** | コードを実行できるようにします。 |
| **`shared`** | イメージを読み込んだすべてのプロセス間でセクションを共有します。 |
| **`nopage`** | セクションをページング不可としてマークします。 Win32 デバイスドライバーに便利です。 |
| **`nocache`** | セクションをキャッシュ不可能としてマークします。 Win32 デバイスドライバーに便利です。 |
| **`discard`** | セクションを破棄不可としてマークします。 Win32 デバイスドライバーに便利です。 |
| **`remove`** | セクションをメモリ常駐ではないとしてマークします。 仮想デバイスドライバー (V *x* D) のみ。 |

属性を指定しない場合、セクションには **`read`** 属性と属性があり **`write`** ます。

## <a name="example"></a>例

この例では、最初のセクションで pragma セクションとその属性を識別します。 を使用して宣言されていないため、整数は `j` に格納されません `mysec` `__declspec(allocate)` 。 代わりに、 `j` データセクションに移動します。 `i` `mysec` ストレージクラス属性が原因で、整数がに `__declspec(allocate)` なります。

```cpp
// pragma_section.cpp
#pragma section("mysec",read,write)
int j = 0;

__declspec(allocate("mysec"))
int i = 0;

int main(){}
```

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
