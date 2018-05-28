---
title: 右シフト | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: c878e97d-ea3c-4c6b-90a8-b1b24b2d5b19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c2eac057bbf8164915ff645cca098bbbf7c1995a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="right-shifts"></a>右シフト
負の値の符号付き整数型の右シフトの結果  
  
 負の値を右へシフトすると、絶対値の 1/2 (切り捨て) になります。 たとえば、符号付きの `short` の値 -253 (16 進で 0xFF03、バイナリで 11111111 00000011) を右に 1 ビット シフトすると、-127 (16 進で 0xFF81、バイナリで 11111111 10000001) になります。 正の 253 を右にシフトすると +126 になります。  
  
 右シフトでは、符号付き整数型の符号ビットが保持されます。 符号付き整数を右にシフトすると、最上位ビットはセットされたままになります。 たとえば、0xF0000000 が符号付き `int` の場合、右にシフトすると 0xF8000000 になります。 負の `int` を右に 32 回シフトすると 0xFFFFFFFF になります。  
  
 符号なし整数を右にシフトすると、最上位ビットはクリアされます。 たとえば、0xF000 が符号なしの場合、結果は 0x7800 です。 `unsigned` または正の `int` を右に 32 回シフトすると、0x00000000 になります。  
  
## <a name="see-also"></a>参照  
 [整数](../c-language/integers.md)