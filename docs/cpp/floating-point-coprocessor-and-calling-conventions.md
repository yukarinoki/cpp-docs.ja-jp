---
title: 浮動小数点コプロセッサと呼び出し規約 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- floating-point numbers [C++]
- floating-point coprocessor
ms.assetid: 3cc6615a-b308-4cf7-9570-83e192a832b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 66ccd54c4abb1d8d9761d5ded88beba76bfae043
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401355"
---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>浮動小数点コプロセッサと呼び出し規則
を作成しているアセンブリ ルーチンが浮動小数点コプロセッサ場合、浮動小数点を保持する必要がある制御ワードをポイントし、返す場合を除き、コプロセッサ スタックをクリーンアップする**float**または**二重**値 (これは、関数は、ST(0)) で返す必要があります。  
  
## <a name="see-also"></a>関連項目  
 [呼び出し規約](../cpp/calling-conventions.md)