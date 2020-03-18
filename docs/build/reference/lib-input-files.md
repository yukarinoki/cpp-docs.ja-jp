---
title: LIB の入力ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
ms.openlocfilehash: 209ba04ea43116b39f28b0790b7a1e2b3fb5ccd7
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439453"
---
# <a name="lib-input-files"></a>LIB の入力ファイル

LIB が必要とする入力ファイルは、次の表に示すように、使用されているモードによって異なります。

|モード|入力|
|----------|-----------|
|既定 (ライブラリの構築または変更)|COFF オブジェクト (.obj) ファイル、COFF ライブラリ (.lib)、32ビットオブジェクトモデルフォーマット (OMF) オブジェクト (.obj) ファイル|
|/EXTRACT を使用してメンバーを抽出する|COFF ライブラリ (.lib)|
|/DEF を使用したエクスポートファイルとインポートライブラリのビルド|モジュール定義 (.def) ファイル、COFF オブジェクト (.obj) ファイル、COFF ライブラリ (.lib)、32ビット OMF オブジェクト (.obj) ファイル|

> [!NOTE]
>  16ビットバージョンの LIB によって作成された OMF ライブラリを、32ビットバージョンの LIB への入力として使用することはできません。

## <a name="see-also"></a>参照

[LIB の概要](overview-of-lib.md)
