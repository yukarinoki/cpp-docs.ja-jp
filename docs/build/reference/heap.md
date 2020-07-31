---
title: /HEAP
description: MSVC リンカーまたは EDITBIN/HEAP オプションは、ヒープの合計サイズと、必要に応じて追加のヒープブロックのサイズを設定します。
ms.date: 07/07/2020
f1_keywords:
- /heap
helpviewer_keywords:
- heap allocation, setting heap size
- HEAP editbin option
- -HEAP editbin option
- /HEAP editbin option
ms.assetid: 6ce759b5-75b7-44ff-a5fd-3a83a0ba9a48
ms.openlocfilehash: 7976ae2927ca731c83fa42e87da182fee4df3d7c
ms.sourcegitcommit: e17cc8a478b51739d67304d7d82422967b35f716
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "86127831"
---
# `/HEAP`

ヒープのサイズをバイト単位で設定します。 このオプションは、実行可能ファイルにのみ適用されます。

## <a name="syntax"></a>構文

> **`/HEAP:`**_`reserve`_\[**`,`**_`commit`_]

## <a name="remarks"></a>解説

引数は、 *`reserve`* 仮想メモリ内の初期ヒープ割り当ての合計を指定します。 **`/HEAP`** リンカーまたは[EDITBIN](editbin-reference.md)オプションは、指定された値を4バイトの最も近い倍数に丸めます。 既定では、ヒープサイズは 1 MB です。

オプションの *`commit`* 引数は、オペレーティングシステムによって解釈される可能性があります。 Windows オペレーティングシステムでは、割り当てられる物理メモリの初期量を指定します。 また、ヒープが展開されるときに割り当てるメモリの量を指定します。 仮想メモリがコミットされると、ページング ファイル内にメモリ空間が予約されます。 値を大きくする *`commit`* と、アプリケーションがより多くのヒープ領域を必要とする場合に、メモリを割り当てる頻度が高くなります。ただし、メモリ要件やアプリの起動時間が長くなる可能性があります。 *`commit`* 値は、値以下である必要があり *`reserve`* ます。 既定値は 4 KB です。

との *`reserve`* 値は、 *`commit`* 10 進数、C 言語の16進数、または8進数の表記で指定します。 たとえば、値 1 MB は10進数で1048576として指定するか、16進数で0x100000 として指定するか、8進数で04000000として指定することができます。 既定値は、オプションに相当し **`/HEAP:1048576,4096`** ます。

### <a name="example"></a>例

この例のリンクコマンドは、ヒープ予約が 2 MB の実行可能*main.exe*を作成します。 初期ヒープとそれ以降のヒープ拡張には、64 KB のブロックがあります。

**`link /heap:0x200000,0x10000 main.obj`**

### <a name="to-set-this-linker-option-in-visual-studio"></a>このリンカー オプションを Visual Studio で設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

1. [**構成プロパティ**] [  >  **リンカー**  >  **システム**] プロパティページを選択します。

1. **ヒープ予約サイズ**と**ヒープコミットサイズ**のプロパティを設定し、[ **OK]** または [**適用**] を選択して変更を保存します。

## <a name="see-also"></a>関連項目

[EDITBIN オプション](editbin-options.md)\
[MSVC リンカー オプション](linker-options.md)
