---
title: LIB の入力ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
ms.openlocfilehash: de81f79eecf3fc73c02894747f4b97cb107cf892
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328227"
---
# <a name="lib-input-files"></a>LIB の入力ファイル

LIB で予期される入力ファイルは、次の表に示すように、使用されているモードによって異なります。

|モード|入力|
|----------|-----------|
|デフォルト (ライブラリの構築または変更)|COFF オブジェクト (.obj) ファイル、COFF ライブラリ (.lib)、32 ビット オブジェクト モデル形式 (OMF) オブジェクト (.obj) ファイル|
|/EXTRACT を使用したメンバーの抽出|COFF ライブラリ (.lib)|
|/DEF を使用してエクスポート ファイルとインポート ライブラリをビルドする|モジュール定義 (.def) ファイル、COFF オブジェクト (.obj) ファイル、COFF ライブラリ (.lib)、32 ビット OMF オブジェクト (.obj) ファイル|

> [!NOTE]
> 16 ビットバージョンの LIB で作成された OMF ライブラリーは、32 ビット版の LIB への入力として使用することはできません。

## <a name="see-also"></a>関連項目

[LIB の概要](overview-of-lib.md)
