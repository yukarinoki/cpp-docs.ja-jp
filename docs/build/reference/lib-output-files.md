---
description: '詳細情報: LIB 出力ファイル'
title: LIB の出力ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- output files, LIB
ms.assetid: e73d2f9b-a42d-402b-b7e3-3a94bebb317e
ms.openlocfilehash: 5a9145f4c75db0c402bc4416cedfd6d63bb23cd4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191070"
---
# <a name="lib-output-files"></a>LIB の出力ファイル

LIB によって生成される出力ファイルは、次の表に示すように、使用されているモードによって異なります。

|モード|出力|
|----------|------------|
|既定 (ライブラリの構築または変更)|COFF ライブラリ (.lib)|
|/EXTRACT を使用してメンバーを抽出する|オブジェクト (.obj) ファイル|
|/DEF を使用したエクスポートファイルとインポートライブラリのビルド|インポートライブラリ (.lib) とエクスポート (.exp) ファイル|

## <a name="see-also"></a>関連項目

[LIB の概要](overview-of-lib.md)
