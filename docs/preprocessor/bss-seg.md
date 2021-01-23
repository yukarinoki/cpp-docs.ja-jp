---
description: pragmaMicrosoft C/c + + での bss_seg ディレクティブの詳細については、こちらを参照してください。
title: bss_seg pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.bss_seg
- bss_seg_CPP
helpviewer_keywords:
- pragma, bss_seg
- bss_seg pragma
no-loc:
- pragma
ms.openlocfilehash: 380d3c465145c3409e86ea6e76cd0b41890574fa
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713091"
---
# <a name="bss_seg-no-locpragma"></a>`bss_seg` pragma

初期化されていない変数がオブジェクト (.obj) ファイルに格納されるセクション (セグメント) を指定します。

## <a name="syntax"></a>構文

> **`#pragma bss_seg(`** ["*section-name*" [ **`,`** "*section-class*"]] **`)`**\
> **`#pragma bss_seg(`**{ **`push`**  |  **`pop`** } [ **`,`** *identifier* ] [ **`,`** "*section-name*" [ **`,`** "*section-class*"]]**`)`**

### <a name="parameters"></a>パラメーター

**`push`**\
Optional内部コンパイラスタックにレコードを格納します。 は **`push`** *識別子* と *セクション名* を持つことができます。

**`pop`**\
Optional内部コンパイラスタックの先頭からレコードを削除します。 は **`pop`** *識別子* と *セクション名* を持つことができます。 識別子を使用して、1つのコマンドだけを使用して複数のレコードをポップでき **`pop`** ます。  *セクション名* は、pop の後のアクティブな BSS セクション名になります。

*identifier*\
Optionalと共に使用すると **`push`** 、内部コンパイラスタックのレコードに名前を割り当てます。 と共に使用すると **`pop`** 、 *識別子* が削除されるまで、ディレクティブによってレコードが内部スタックからポップされます。 *識別子* が内部スタックで見つからない場合は、何もポップされません。

*"section-name"*\
Optionalセクションの名前。 と共に使用すると **`pop`** 、スタックがポップされ、 *セクション名* がアクティブな BSS セクション名になります。

*"セクション-クラス"*\
Optionalは無視されますが、バージョン2.0 より前のバージョンの Microsoft C++ との互換性のために含まれています。

## <a name="remarks"></a>解説

オブジェクトファイルの *セクション* は、1つの単位としてメモリに読み込まれるデータの名前付きブロックです。 *BSS セクション* は、初期化されていないデータを含むセクションです。 この記事では、 *セグメント* と *セクション* は同じ意味を持ちます。

ディレクティブは、初期化されて **`bss_seg`** pragma いないすべてのデータ項目を、翻訳単位から *セクション名* という名前の BSS セクションに配置するようコンパイラに指示します。 場合によっ **`bss_seg`** ては、初期化されていないデータを1つのセクションにグループ化することによって、読み込み時間を短縮できます。 既定では、オブジェクトファイル内の初期化されていないデータに使用される BSS セクションにはという名前が付けられ `.bss` ます。 **`bss_seg`** pragma *セクション名* パラメーターのないディレクティブは、後続の初期化されていないデータ項目の BSS セクション名をにリセット `.bss` します。

を使用して割り当てられたデータ **`bss_seg`** pragma は、その場所に関する情報を保持しません。

セクションの作成に使用しない名前の一覧については、「」を参照してください [`/SECTION`](../build/reference/section-specify-section-attributes.md) 。

初期化されたデータのセクション ( [`data_seg`](../preprocessor/data-seg.md) )、関数 ( [`code_seg`](../preprocessor/code-seg.md) )、および const 変数 () を指定することもでき [`const_seg`](../preprocessor/const-seg.md) ます。

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

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
