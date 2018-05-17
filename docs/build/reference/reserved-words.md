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
ms.openlocfilehash: abe67e1804d436dbd44257f6d7670a71b7f74889
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="reserved-words"></a>予約語
次の単語は、リンカーによって予約されています。 これらの名前を引数として使用できます[モジュール定義ステートメント](../../build/reference/module-definition-dot-def-files.md)名前が二重引用符で囲まれている場合にのみ ("") です。  
  
||||  
|-|-|-|  
|**APPLOADER**1|**INITINSTANCE**2|**プリロード**|  
|**ベース**|**に対しては IOPL**|**プライベート**|  
|**コード**|**ライブラリ**1|**PROTMODE**2|  
|**準拠しています。**|**LOADONCALL**1|**純粋な**1|  
|**データ**|**LONGNAMES**2|**READONLY**|  
|**説明**|**移動可能な**1|**読み取り/書き込み**|  
|**DEV386**|**MOVEABLE**1|**リアルモード**1|  
|**破棄可能**|**複数**|**常駐**|  
|**動的**|**NAME**|**RESIDENTNAME**1|  
|**実行専用**|**NEWFILES**2|**セクション**|  
|**EXECUTEONLY**|**NODATA**1|**セグメント**|  
|**読み取り**|**NOIOPL**1|**共有**|  
|**EXETYPE**|**NONAME**|**1 つ**|  
|**エクスポート**|**準拠していない**1|**スタックサイズ**|  
|**固定**1|**NONDISCARDABLE**|**スタブ**|  
|**関数**2|**[なし]**|**バージョン**|  
|**ヒープサイズ**|**非共有**|**WINDOWAPI**|  
|**インポート**|**NOTWINDOWCOMPAT**1|**WINDOWCOMPAT**|  
|**純粋でない**1|**オブジェクト**|**WINDOWS**|  
|**含める**2|**古い**1||  
  
 1 この用語に到達したときに、、リンカーは (「無視」)、警告を出力します。 ただし、単語は、まだ予約されています。  
  
 2、リンカーは、この単語は無視されますが、警告は出力されません。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)