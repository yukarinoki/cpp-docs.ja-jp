---
title: LIB の出力ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- output files, LIB
ms.assetid: e73d2f9b-a42d-402b-b7e3-3a94bebb317e
ms.openlocfilehash: 8aeb46b0249ddf4155277866f7d8537bbfa98244
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439376"
---
# <a name="lib-output-files"></a>LIB の出力ファイル

LIB によって生成される出力ファイルは、次の表に示すように、使用されているモードによって異なります。

|モード|出力|
|----------|------------|
|既定 (ライブラリの構築または変更)|COFF ライブラリ (.lib)|
|/EXTRACT を使用してメンバーを抽出する|オブジェクト (.obj) ファイル|
|/DEF を使用したエクスポートファイルとインポートライブラリのビルド|インポートライブラリ (.lib) とエクスポート (.exp) ファイル|

## <a name="see-also"></a>参照

[LIB の概要](overview-of-lib.md)
