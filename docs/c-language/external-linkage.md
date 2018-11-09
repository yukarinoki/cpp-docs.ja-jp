---
title: 外部リンケージ
ms.date: 11/04/2016
helpviewer_keywords:
- linkage [C++], external
- external linkage, about external linkage
- external linkage
ms.assetid: a6f8ea69-b405-4cdd-bf12-ad5462b73183
ms.openlocfilehash: 87e9e16eb115df8d100450f7f0dc44961886ab20
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466262"
---
# <a name="external-linkage"></a>外部リンケージ

ID のファイル スコープ レベルの最初の宣言で **static** ストレージ クラス指定子を使用していない場合、オブジェクトに外部リンケージがあります。

関数の ID の宣言に *storage-class-specifier* がない場合、そのリンケージは、*storage-class-specifier* `extern` で宣言されている場合とまったく同じように決定されます。 オブジェクトの ID の宣言にファイル スコープがあり、*storage-class-specifier* が含まれていない場合、リンケージは外部になります。

外部リンケージを持つ識別子の名前は、外部リンケージを持つ同じ名前の他の宣言で指定されるものと同じ関数またはデータ オブジェクトを指定します。 2 つの宣言を同じ翻訳単位または異なる翻訳単位に配置できます。 オブジェクトまたは関数にグローバル有効期間もある場合、オブジェクトまたは関数はプログラム全体で共有されます。

## <a name="see-also"></a>参照

[extern を使用したリンケージの指定](../cpp/using-extern-to-specify-linkage.md)