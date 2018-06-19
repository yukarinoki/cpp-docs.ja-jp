---
title: ビット フィールド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- bitfields
ms.assetid: e9a1010d-1e1b-487f-9943-3c574e08f544
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 85db49f138cc733326e47a3008e79bae5ab4b7cb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360781"
---
# <a name="bitfields"></a>ビット フィールド
構造体のビット フィールドは 64 ビットに制限されており、型は int、unsigned int 型、int64、または符号なしの int64 の署名します。 型の境界を越えることがビット フィールドでは、[次へ] の型のアラインメントをビット フィールドを配置するをスキップします。 たとえば、整数のビット フィールドを超えることは 32 ビットの境界。  
  
## <a name="see-also"></a>関連項目  
 [型とストレージ](../build/types-and-storage.md)