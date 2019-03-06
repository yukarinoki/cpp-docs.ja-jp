---
title: LIB の出力ファイル
ms.date: 11/04/2016
f1_keywords:
- Lib
helpviewer_keywords:
- output files, LIB
ms.assetid: e73d2f9b-a42d-402b-b7e3-3a94bebb317e
ms.openlocfilehash: 31c69a273d9f201046171ecc8889dda6e07328d6
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57419323"
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
