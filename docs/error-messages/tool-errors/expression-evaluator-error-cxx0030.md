---
title: 式エバリュエーター エラー CXX0030 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0030
dev_langs:
- C++
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 669c585c637129c1fb6a480d91b31e5a1264fd22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298117"
---
# <a name="expression-evaluator-error-cxx0030"></a>式エバリュエーター エラー CXX0030
評価できない式  
  
 書き込まれると、デバッガーの式エバリュエーターは式の値を取得できませんでした。 1 つの考えられる原因は、式が外部プログラムのアドレス空間にあるメモリを指すこと (1 つの例では null ポインターの逆参照)。 Windows は、プログラムのアドレス空間の外部では、メモリへのアクセスを許可しません。  
  
 評価の順序を制御するかっこを使用して、式を書き直すことができます。  
  
 このエラーは、can0030 と同じものと同じです。