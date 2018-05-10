---
title: LIB の入力ファイル |Microsoft ドキュメント
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
ms.openlocfilehash: 140a0f1d9ef6fdb3ca5e6d6977804684c88af1fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="lib-input-files"></a>LIB の入力ファイル
LIB で想定されている入力ファイルは、次の表に示すように、モードによって異なります。  
  
|モード|入力|  
|----------|-----------|  
|既定値 (構築またはライブラリの変更)|COFF オブジェクト (.obj) ファイル、COFF ライブラリ (.lib)、32 ビット omf オブジェクト モデルの形式 (です) のオブジェクト (.obj) ファイル|  
|/EXTRACT を持つメンバーを抽出します。|COFF ライブラリ (.lib)|  
|ファイルの構築では、エクスポートとインポート ライブラリ/DEF の|モジュール定義 (.def) ファイル、COFF オブジェクト (.obj) ファイル、COFF ライブラリ (.lib)、32 ビット OMF オブジェクト (.obj) ファイル|  
  
> [!NOTE]
>  LIB の 16 ビット バージョンで作成した OMF ライブラリは、LIB の 32 ビット バージョンへの入力として使用できません。  
  
## <a name="see-also"></a>関連項目  
 [LIB の概要](../../build/reference/overview-of-lib.md)