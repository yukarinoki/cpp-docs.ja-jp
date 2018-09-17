---
title: LIB の入力ファイル |マイクロソフトのドキュメント
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
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 952c3345234192e3798fea483d527cd3afec4bff
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702469"
---
# <a name="lib-input-files"></a>LIB の入力ファイル

LIB で想定されている入力ファイルは、次の表に示すように、モードによって異なります。

|モード|入力|
|----------|-----------|
|既定値 (構築またはライブラリの変更)|COFF オブジェクト (.obj) ファイル、32 ビット omf オブジェクト モデルの形式 (です) のオブジェクト (.obj) ファイルである COFF ライブラリ (.lib)|
|/EXTRACT でメンバーの抽出|COFF ライブラリ (.lib)|
|ファイルし、/DEF ライブラリをインポート、エクスポートの構築|モジュール定義 (.def) ファイル、COFF オブジェクト (.obj) ファイル、COFF ライブラリ (.lib)、32 ビット OMF オブジェクト (.obj) ファイル|

> [!NOTE]
>  16 ビット版の LIB によって作成された OMF ライブラリは、LIB の 32 ビット バージョンへの入力として使用できません。

## <a name="see-also"></a>関連項目

[LIB の概要](../../build/reference/overview-of-lib.md)