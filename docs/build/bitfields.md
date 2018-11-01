---
title: ビット フィールド
ms.date: 11/04/2016
helpviewer_keywords:
- bitfields
ms.assetid: e9a1010d-1e1b-487f-9943-3c574e08f544
ms.openlocfilehash: 3ff0092bbd31b8b1cd98fa56fb802c7ce28cb472
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652830"
---
# <a name="bitfields"></a>ビット フィールド

構造体のビット フィールドは 64 ビットに制限されており、型は int、unsigned int、int64、または unsigned int64 の署名します。 型の境界を越えるビット フィールドでは、次の型の配置をビット フィールドを配置するをスキップします。 たとえば、整数のビット フィールド可能性があります、32 ビットの境界を通過しません。

## <a name="see-also"></a>関連項目

[型とストレージ](../build/types-and-storage.md)