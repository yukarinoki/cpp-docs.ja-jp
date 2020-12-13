---
description: '詳細情報: section プラグマ'
title: section プラグマ
ms.date: 08/29/2019
f1_keywords:
- section_CPP
- vc-pragma.section
helpviewer_keywords:
- pragmas, section
- section pragma
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
ms.openlocfilehash: f4a719c60fd5bdf4f8e8841aab88f82c30b92a95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342284"
---
# <a name="section-pragma"></a>section プラグマ

.obj ファイルにセクションを作成します。

## <a name="syntax"></a>構文

> **#pragma セクション (** "*section-name*" [ **,** *attributes* ] **)**

## <a name="remarks"></a>解説

この記事では、 *セグメント* と *セクション* という用語は同じ意味を持ちます。

セクションを定義すると、そのセクションはそれ以降のコンパイルで有効になります。 ただし、 [__declspec (割り当て)](../cpp/allocate.md)を使用するか、セクションに何も配置しないようにする必要があります。

*section-name* は、セクションの名前になる必須パラメーターです。 標準セクション名と競合する名前は付けられません。 セクションを作成するときに使用しない名前の一覧については、「 [/SECTION](../build/reference/section-specify-section-attributes.md) 」を参照してください。

*attributes* は、セクションに割り当てる1つ以上のコンマ区切りの属性で構成される省略可能なパラメーターです。 使用できる *属性* は次のとおりです。

|属性|説明|
|-|-|
|**込ん**|データの読み取り操作を有効にします。|
|**企画**|データの書き込み操作を有効にします。|
|**execute**|コードを実行できるようにします。|
|**共用**|イメージを読み込んだすべてのプロセス間でセクションを共有します。|
|**nopage**|セクションをページング不可としてマークします。 Win32 デバイスドライバーに便利です。|
|**nocache**|セクションをキャッシュ不可能としてマークします。 Win32 デバイスドライバーに便利です。|
|**反映**|セクションを破棄不可としてマークします。 Win32 デバイスドライバーに便利です。|
|**remove**|セクションをメモリ常駐ではないとしてマークします。 仮想デバイスドライバー (V *x* D) のみ。|

属性を指定しない場合、セクションには **読み取り** 属性と **書き込み** 属性があります。

## <a name="example"></a>例

この例では、最初のセクションのプラグマはセクションとその属性を識別します。 を使用して宣言されていないため、整数 `j` はに格納されません `mysec` `__declspec(allocate)` 。 代わりに、 `j` データセクションに移動します。 整数 `i` は、その `mysec` ストレージ クラス属性の結果として `__declspec(allocate)` に追加されます。

```cpp
// pragma_section.cpp
#pragma section("mysec",read,write)
int j = 0;

__declspec(allocate("mysec"))
int i = 0;

int main(){}
```

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
