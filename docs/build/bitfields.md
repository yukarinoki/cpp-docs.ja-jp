---
title: ビット フィールド |マイクロソフトのドキュメント
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
ms.openlocfilehash: a7451ea6afee81cc296fb091705bde48041ef5d1
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722489"
---
# <a name="bitfields"></a>ビット フィールド

構造体のビット フィールドは 64 ビットに制限されており、型は int、unsigned int、int64、または unsigned int64 の署名します。 型の境界を越えるビット フィールドでは、次の型の配置をビット フィールドを配置するをスキップします。 たとえば、整数のビット フィールド可能性があります、32 ビットの境界を通過しません。

## <a name="see-also"></a>関連項目

[型とストレージ](../build/types-and-storage.md)