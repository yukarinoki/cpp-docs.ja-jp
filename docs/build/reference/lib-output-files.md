---
title: LIB の出力ファイル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- Lib
dev_langs:
- C++
helpviewer_keywords:
- output files, LIB
ms.assetid: e73d2f9b-a42d-402b-b7e3-3a94bebb317e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8caa26685d6132cbc1ffd8a2467f8615bffd42f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32370489"
---
# <a name="lib-output-files"></a>LIB の出力ファイル
LIB によって生成された出力ファイルは、次の表に示すように、モードによって異なります。  
  
|モード|出力|  
|----------|------------|  
|既定値 (構築またはライブラリの変更)|COFF ライブラリ (.lib)|  
|/EXTRACT を持つメンバーを抽出します。|オブジェクト (.obj) ファイル|  
|ファイルの構築では、エクスポートとインポート ライブラリ/DEF の|インポート ライブラリ (.lib) とエクスポート (.exp) ファイル|  
  
## <a name="see-also"></a>関連項目  
 [LIB の概要](../../build/reference/overview-of-lib.md)