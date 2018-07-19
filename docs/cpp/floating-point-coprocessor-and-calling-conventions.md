---
title: 浮動小数点コプロセッサと呼び出し規約 |Microsoft ドキュメント
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
ms.openlocfilehash: 46cf9c937453894ed37ad434ad94609d0744be24
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32410802"
---
# <a name="floating-point-coprocessor-and-calling-conventions"></a>浮動小数点コプロセッサと呼び出し規則
場合は、作成しているアセンブリ ルーチンを浮動小数点コプロセッサ浮動を保持する必要がある制御ワードをポイントし、コプロセッサ スタックをクリーンアップするを返す場合を除き、 **float**または**二重**(値が、関数は、ST(0)) で返す必要があります。  
  
## <a name="see-also"></a>関連項目  
 [呼び出し規約](../cpp/calling-conventions.md)