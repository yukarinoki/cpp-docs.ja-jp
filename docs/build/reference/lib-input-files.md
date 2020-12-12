---
description: '詳細情報: LIB 入力ファイル'
title: LIB の入力ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
ms.openlocfilehash: f40cba91f0772e0073daca20a8f2093f3eec8aec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199546"
---
# <a name="lib-input-files"></a>LIB の入力ファイル

LIB が必要とする入力ファイルは、次の表に示すように、使用されているモードによって異なります。

|モード|入力|
|----------|-----------|
|既定 (ライブラリの構築または変更)|COFF オブジェクト (.obj) ファイル、COFF ライブラリ (.lib)、32ビットオブジェクトモデルフォーマット (OMF) オブジェクト (.obj) ファイル|
|/EXTRACT を使用してメンバーを抽出する|COFF ライブラリ (.lib)|
|/DEF を使用したエクスポートファイルとインポートライブラリのビルド|モジュール定義 (.def) ファイル、COFF オブジェクト (.obj) ファイル、COFF ライブラリ (.lib)、32ビット OMF オブジェクト (.obj) ファイル|

> [!NOTE]
> 16ビットバージョンの LIB によって作成された OMF ライブラリを、32ビットバージョンの LIB への入力として使用することはできません。

## <a name="see-also"></a>関連項目

[LIB の概要](overview-of-lib.md)
