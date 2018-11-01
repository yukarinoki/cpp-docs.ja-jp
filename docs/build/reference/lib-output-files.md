---
title: LIB の出力ファイル
ms.date: 11/04/2016
f1_keywords:
- Lib
helpviewer_keywords:
- output files, LIB
ms.assetid: e73d2f9b-a42d-402b-b7e3-3a94bebb317e
ms.openlocfilehash: bc505a9a946f564425513dad8107fd962eb054b9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562900"
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