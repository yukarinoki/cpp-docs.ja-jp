---
title: 致命的なエラー C1383 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1383
dev_langs:
- C++
helpviewer_keywords:
- C1383
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ae5e16959597e16f25320778be4d4b45ca5950e0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33226975"
---
# <a name="fatal-error-c1383"></a>致命的なエラー C1383
コンパイラ オプション /GL は、インストールされた共通言語ランタイムのバージョンと互換性がありません  
  
 C1383 は、共通言語ランタイムの以前のバージョンをそれより新しいコンパイラで使用しているときに、 **/clr** と **/GL.** を指定してコンパイルすると発生します。  
  
 解決するには、 **/GL** を **/clr** と共に使用しないようにするか、使用しているコンパイラに付属している共通言語ランタイムのバージョンをインストールします。  
  
 詳細については、 [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) および [/GL (Whole Program Optimization)](../../build/reference/gl-whole-program-optimization.md)を参照してください。