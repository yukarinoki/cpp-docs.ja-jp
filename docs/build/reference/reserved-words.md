---
title: 予約語
ms.date: 11/04/2016
f1_keywords:
- code
- CONFORMING
- DISCARDABLE
- Description
- base
- APPLOADER
- Data
- DYNAMIC
- DEV386
helpviewer_keywords:
- .def files [C++], reserved words
- def files [C++], reserved words
- linker [C++], reserved words
- reserved words [C++]
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
ms.openlocfilehash: 16caacb77e052eebc8e2cd101990ee373535bd6e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171152"
---
# <a name="reserved-words"></a>予約語

次の単語は、リンカーによって予約されています。 これらの名前は、名前が二重引用符 ("") で囲まれている場合にのみ、[モジュール定義ステートメント](module-definition-dot-def-files.md)の引数として使用できます。

||||
|-|-|-|
|\- **Oader**<sup>1</sup>|**INITINSTANCE**<sup>2</sup>|**読み込ま**|
|**常用**|**IOPL**|**プライバシー**|
|**コード**|**ライブラリ**<sup>1</sup>|**PROTMODE**<sup>2</sup>|
|**適合**|**Loadoncall**<sup>1</sup>|**純粋**<sup>1</sup>|
|**データ**|**Longnames**<sup>2</sup>|**READONLY**|
|**説明**|**MOVABLE**移動可能<sup>1</sup>|**読み書き**|
|**DEV386**|**MOVEABLE**移動可能<sup>1</sup>|**Realmode**<sup>1</sup>|
|**アンドゥ**|**複数**|**TSR**|
|**動的**|**名前**|**RESIDENTNAME**<sup>1</sup>|
|**実行専用**|**Newfiles**<sup>2</sup>|**各項**|
|**EXECUTEONLY**|**NODATA**<sup>1</sup>|**楕円**|
|**EXECUTEREAD**|**NOIOPL**<sup>1</sup>|**共用**|
|**EXETYPE**|**ボード**|**1**|
|**エクスポート**|**不適合**<sup>1</sup>|**スタックサイズ**|
|**修正**済み<sup>1</sup>|**非破棄**|**スタブ**|
|**関数**<sup>2</sup>|**NONE**|**VERSION**|
|**ヒープサイズ**|**共有**|**WINDOWAPI**|
|**取り込ま**|**Notwindowcompat**<sup>1</sup>|**WINDOWCOMPAT**|
|**純粋でない**<sup>1</sup>|**表す**|**ウィンドウ**|
|**INCLUDE**<sup>2</sup>を含める|**OLD**<sup>1</sup>||

<sup>1</sup>リンカーは、この用語が検出されたときに警告 ("無視") を出力します。 ただし、この単語は予約されたままです。

<sup>2</sup>リンカーはこの単語を無視しますが、警告は出力しません。

## <a name="see-also"></a>参照

- [MSVC リンカーのリファレンス](linking.md)
- [MSVC リンカー オプション](linker-options.md)
