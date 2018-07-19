---
title: CObject から新しくクラスを派生する必要性 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 51904ac06ae6c2db5586f8dc405f85145c5b1f30
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343061"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>CObject から新しくクラスを派生する必要性
必要はありません。  
  
 クラスを派生[CObject](../mfc/reference/cobject-class.md) 、用意されているシリアル化やダイナミック creatability などの機能を必要とします。 多くの場合、それらから派生することをお勧めようにファイルにシリアル化する必要があるデータ クラスの多く`CObject`です。 派生したクラスの例の`CObject`を参照してください、 [Scribble サンプル](../visual-cpp-samples.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス: Q & A 集](../mfc/cobject-class-frequently-asked-questions.md)
