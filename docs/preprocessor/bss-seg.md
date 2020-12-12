---
description: '詳細については、次を参照してください: bss_seg プラグマ'
title: bss_seg プラグマ
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.bss_seg
- bss_seg_CPP
helpviewer_keywords:
- pragmas, bss_seg
- bss_seg pragma
ms.assetid: 755f0154-de51-4778-97d3-c9b24e445079
ms.openlocfilehash: e7a2cf73f8ab542755e5f6e0183896ce8e64be2a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300880"
---
# <a name="bss_seg-pragma"></a>bss_seg プラグマ

初期化されていない変数がオブジェクト (.obj) ファイルに格納されるセクション (セグメント) を指定します。

## <a name="syntax"></a>構文

> **#pragma bss_seg (** ["*section-name*" [ **,** "*section-class*"]] **)**\
> **#pragma bss_seg (** { **push**  |  **pop** } [ **,** *identifier* ] [ **,** "*section-name*" [ **,** "*section-class*"]] **)**

### <a name="parameters"></a>パラメーター

**押し付け**\
Optional内部コンパイラスタックにレコードを格納します。 **プッシュ** は *識別子* と *セクション名* を持つことができます。

**ショート**\
Optional内部コンパイラスタックの先頭からレコードを削除します。 **Pop** は *識別子* と *セクション名* を持つことができます。 *識別子* を使用して、 **pop** コマンドを1つだけ使用して複数のレコードをポップできます。 *セクション名* は、pop の後のアクティブな BSS セクション名になります。

*identifier*\
Optional **Push** と共に使用すると、内部コンパイラスタックのレコードに名前が割り当てられます。 **Pop** と共に使用する場合、ディレクティブは、*識別子* が削除されるまで、レコードを内部スタックからポップします。 *識別子* が内部スタックで見つからない場合は、何もポップされません。

*"section-name"*\
Optionalセクションの名前。 **Pop** と共に使用すると、スタックがポップされ、*セクション名* がアクティブな BSS セクション名になります。

*"セクション-クラス"*\
Optionalは無視されますが、バージョン2.0 より前のバージョンの Microsoft C++ との互換性のために含まれています。

## <a name="remarks"></a>解説

オブジェクトファイルの *セクション* は、1つの単位としてメモリに読み込まれるデータの名前付きブロックです。 *BSS セクション* は、初期化されていないデータを含むセクションです。 この記事では、 *セグメント* と *セクション* は同じ意味を持ちます。

**Bss_seg** pragma ディレクティブは、初期化されていないすべてのデータ項目を、翻訳単位から *セクション名* という名前の bss セクションに配置するようコンパイラに指示します。 場合によっては、初期化されていないデータを1つのセクションにグループ化することで、 **bss_seg** を使用すると読み込み時間を短縮できます。 既定では、オブジェクトファイル内の初期化されていないデータに使用される BSS セクションにはという名前が付けられ `.bss` ます。 *セクション名* パラメーターを指定せずに **bss_seg** プラグマディレクティブを実行すると、後続の初期化されていないデータ項目の bss セクション名がにリセットされ `.bss` ます。

**Bss_seg** プラグマを使用して割り当てられたデータは、その場所に関する情報を保持しません。

セクションの作成に使用しない名前の一覧については、「 [/SECTION](../build/reference/section-specify-section-attributes.md)」を参照してください。

初期化されたデータのセクション ([data_seg](../preprocessor/data-seg.md))、関数 ([code_seg](../preprocessor/code-seg.md))、および const 変数 ([const_seg](../preprocessor/const-seg.md)) を指定することもできます。

[DUMPBIN.EXE](../build/reference/dumpbin-command-line.md)アプリケーションを使用して、オブジェクトファイルを表示できます。 サポートされている各ターゲットアーキテクチャの DUMPBIN のバージョンは、Visual Studio に含まれています。

## <a name="example"></a>例

```cpp
// pragma_directive_bss_seg.cpp
int i;                     // stored in .bss
#pragma bss_seg(".my_data1")
int j;                     // stored in .my_data1

#pragma bss_seg(push, stack1, ".my_data2")
int l;                     // stored in .my_data2

#pragma bss_seg(pop, stack1)   // pop stack1 from stack
int m;                     // stored in .my_data1

int main() {
}
```

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
