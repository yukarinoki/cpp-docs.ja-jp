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
ms.openlocfilehash: ec080e556b57afadbc3d958f4dba5ac6393108aa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408909"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>CObject から新しくクラスを派生する必要性

いいえ、ありません。

クラスを派生[CObject](../mfc/reference/cobject-class.md)がでシリアル化やダイナミック creatability などの機能を必要がある場合。 データ クラスの多くは、ため、多くの場合からも派生することをお勧めのファイルにシリアル化する必要があります`CObject`します。 派生したクラスの例の`CObject`を参照してください、 [Scribble サンプル](../visual-cpp-samples.md)します。

## <a name="see-also"></a>関連項目

[CObject クラス: Q & A 集](../mfc/cobject-class-frequently-asked-questions.md)
