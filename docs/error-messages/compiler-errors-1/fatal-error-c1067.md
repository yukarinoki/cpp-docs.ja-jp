---
title: 致命的なエラー C1067 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1067
dev_langs:
- C++
helpviewer_keywords:
- C1067
ms.assetid: e2c94be6-4573-4571-aac9-73d657fe9f96
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 89ac7084e92f7f2ed496a4c1572e94a4fa46862f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229093"
---
# <a name="fatal-error-c1067"></a>致命的なエラー C1067
コンパイラの制限: 型のレコード サイズの 64 K の制限を超えています  
  
 このエラーは、シンボルは、247 文字を超える装飾された名前を持つ場合に発生する可能性があります。  を解決するのには、シンボル名を短くしてください。  
  
 コンパイラは、デバッグ情報を生成するときに、ソース コードで検出された型を定義するタイプのレコードを出力します。  たとえば、型のレコードには、単純な構造体と関数の引数リストが含まれます。  大きなリスト型レコードのことができます。  
  
 任意の種類のレコードのサイズに 64 K の制限があります。  その 64 K の制限を超えた場合、このエラーが発生します。  
  
 C1067 は、長い名前を持つ多数のシンボルがある場合、またはクラス、構造体、または共用体がメンバーが多すぎる場合にも発生することができます。