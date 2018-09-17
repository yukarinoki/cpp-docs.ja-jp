---
title: LIB の出力ファイル |Microsoft Docs
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
ms.openlocfilehash: 23665897266bab87c71b8b3889688113fe8aa99a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720708"
---
# <a name="lib-output-files"></a>LIB の出力ファイル

LIB によって生成された出力ファイルは、次の表に示すように、モードによって異なります。

|モード|出力|
|----------|------------|
|既定値 (構築またはライブラリの変更)|COFF ライブラリ (.lib)|
|/EXTRACT でメンバーの抽出|オブジェクト (.obj) ファイル|
|ファイルし、/DEF ライブラリをインポート、エクスポートの構築|ライブラリ (.lib) とエクスポート (.exp) ファイルをインポートします。|

## <a name="see-also"></a>関連項目

[LIB の概要](../../build/reference/overview-of-lib.md)