---
title: 予約語 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- .def files [C++], reserved words
- def files [C++], reserved words
- linker [C++], reserved words
- reserved words [C++]
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 132bd8e5ba66cbf9486a6da4747994c667e2f6e7
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705661"
---
# <a name="reserved-words"></a>予約語

次の単語は、リンカーによって予約されています。 これらの名前を引数として使用できます[モジュール定義ステートメント](../../build/reference/module-definition-dot-def-files.md)名前が二重引用符で囲まれている場合にのみ ("") です。

||||
|-|-|-|
|**APPLOADER**<sup>1</sup>|**INITINSTANCE**<sup>2</sup>|**プリロード**|
|**ベース**|**に対しては IOPL**|**プライベート**|
|**コード**|**ライブラリ**<sup>1</sup>|**PROTMODE**<sup>2</sup>|
|**準拠しています。**|**LOADONCALL**<sup>1</sup>|**純粋な**<sup>1</sup>|
|**データ**|**LONGNAMES**<sup>2</sup>|**READONLY**|
|**説明**|**移動可能な**<sup>1</sup>|**読み取り/書き込み**|
|**DEV386**|**MOVEABLE**<sup>1</sup>|**リアルモード**<sup>1</sup>|
|**破棄可能**|**複数**|**常駐**|
|**動的**|**NAME**|**RESIDENTNAME**<sup>1</sup>|
|**実行専用**|**NEWFILES**<sup>2</sup>|**セクション**|
|**EXECUTEONLY**|**NODATA**<sup>1</sup>|**セグメント**|
|**読み取り**|**NOIOPL**<sup>1</sup>|**共有**|
|**EXETYPE**|**NONAME**|**1 つ**|
|**エクスポート**|**準拠していない**<sup>1</sup>|**スタックサイズ**|
|**固定**<sup>1</sup>|**NONDISCARDABLE**|**スタブ**|
|**関数**<sup>2</sup>|**[なし]**|**バージョン**|
|**ヒープサイズ**|**非共有**|**WINDOWAPI**|
|**インポート**|**NOTWINDOWCOMPAT**<sup>1</sup>|**WINDOWCOMPAT**|
|**純粋でない**<sup>1</sup>|**オブジェクト**|**WINDOWS**|
|**含める**<sup>2</sup>|**古い**<sup>1</sup>||

<sup>1</sup>この用語を検出すると、リンカーは警告 (「無視」) を生成します。 ただし、単語は、まだ予約されています。

<sup>2</sup>リンカーは、この単語を無視しますが、警告は出力されません。

## <a name="see-also"></a>関連項目

- [リンカー オプションの設定](../../build/reference/setting-linker-options.md)
- [リンカー オプション](../../build/reference/linker-options.md)