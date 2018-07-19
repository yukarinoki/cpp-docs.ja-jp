---
title: 集約と共用体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- aggregates [C++], and unions
ms.assetid: 859fc211-b111-4f12-af98-de78e48f9b92
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5b1afd3be89e1d18da9889d88dbbbef3fb104e02
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363260"
---
# <a name="aggregates-and-unions"></a>集約と共用体
配列、構造体、および共用体などの他の種類には、確実に一貫した集約と共用体記憶域とデータ取得厳しいアラインメント要件があります。 配列、構造、および共用体の定義を次に示します。  
  
 配列  
 連続するデータ オブジェクトの順序付きのグループが含まれています。 各オブジェクトには、要素は呼び出されます。 配列内のすべての要素は、同じサイズとデータ型を持ちます。  
  
 構造体  
 データ オブジェクトの順序付きのグループが含まれています。 、配列の要素とは異なり、構造内のデータ オブジェクトは別のデータ型やサイズを持つことができます。 構造体の各データ オブジェクトには、メンバーが呼び出されます。  
  
 和集合  
 名前付きのメンバーのセットのいずれかを保持するオブジェクト。 名前付きセットのメンバーは、任意の型であることができます。 共用体に割り当てられた記憶域は、最大のメンバーを共用体の配置に必要なすべての埋め込みに必要なストレージになります。  
  
 次の表は、強く推奨される、スカラー共用体と構造体のメンバーのアラインメントを示します。  
  
||||  
|-|-|-|  
|スカラー型|C データ型|必要な配置|  
|**INT8**|`char`|Byte|  
|**UINT8**|`unsigned char`|Byte|  
|**INT16**|**short**|Word|  
|**UINT16**|**unsigned short**|Word|  
|**INT32**|**int、long**|ダブルワード|  
|**UINT32**|**符号なし int、unsigned long**|ダブルワード|  
|**INT64**|`__int64`|Quadword|  
|**UINT64**|**unsigned __int64**|Quadword|  
|**FP32 (1 つの有効桁数)**|**float**|ダブルワード|  
|**FP64 (有効桁数を 2 つ)**|**double**|Quadword|  
|**ポインター**|**\***|Quadword|  
|`__m64`|**構造体 _ _m64**|Quadword|  
|`__m128`|**_ _m128 の構造体**|Octaword|  
  
 次の集計の配置ルールが適用されます。  
  
-   配列の配置では、配列の要素の 1 つの配置と同じです。  
  
-   構造体または共用体の先頭のアラインメントは、個々 のメンバーの最大の配置です。 構造体または共用体の各メンバーは、前のメンバーによって、暗黙の型の内部パディングがかかる場合、前の表で定義されている、適切なアラインメントに配置する必要があります。  
  
-   構造体のサイズは、その配置では、最後のメンバーの後にスペースを必要がありますの整数倍である必要があります。 構造体と共用体は、配列でグループ化することができます、ので構造体または共用体の配列の各要素の最初し、最後、適切なアラインメントが以前にします。  
  
-   以前のルールを管理する限りのアラインメント要件よりも大きい値を指定するようにデータを配置することができます。  
  
-   個々 のコンパイラでは、サイズ上の理由から、構造体のパッキングを調整できます。 たとえば[/Zp (構造体メンバーの配置)](../build/reference/zp-struct-member-alignment.md)により、構造体のパッキングを調整します。  
  
## <a name="see-also"></a>関連項目  
 [型とストレージ](../build/types-and-storage.md)
