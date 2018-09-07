---
title: スカラー型 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 07c9195e-b6c7-4083-8ef0-8a93032e4d1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6af598ec6e27138f4e666007018ce803177697b3
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211142"
---
# <a name="scalar-types"></a>スカラー型
データへのアクセスは、任意の配置を生じることができます、データがパフォーマンスの損失 (またはその倍数) を回避するために自然な境界に合わせて調整することをお勧めします。 列挙型が定数の整数であり、32 ビット整数として扱われます。 次のアラインメント値を使用して配置に関連している、次の表に、によって、型の定義と推奨される記憶域が説明します。  
  
-   8 ビット バイト  
  
-   Word の 16 ビット  
  
-   ダブル ワード - 32 ビット  
  
-   クアッドにひと言 - 64 ビット  
  
-   オクタワード - 128 ビット  
  
|||||  
|-|-|-|-|  
|スカラー型|C データ型|ストレージ サイズ (バイト単位)|推奨される配置|  
|**INT8**|**char**|1|Byte|  
|**UINT8**|**unsigned char**|1|Byte|  
|**INT16**|**short**|2|Word|  
|**UINT16**|**unsigned short**|2|Word|  
|**INT32**|**int**、**長**|4|ダブルワード|  
|**UINT32**|**符号なし int、unsigned long**|4|ダブルワード|  
|**INT64**|**__int64**|8|Quadword|  
|**UINT64**|**unsigned __int64**|8|Quadword|  
|**FP32 (単一の有効桁数)**|**float**|4|ダブルワード|  
|**FP64 (有効桁数を 2 倍)**|**double**|8|Quadword|  
|**ポインター**|<strong>\*</strong>|8|Quadword|  
|**__m64**|**構造体の _ _m64**|8|Quadword|  
|**__m128**|**_ _m128 の構造体**|16|Octaword|  
  
## <a name="see-also"></a>関連項目  
 [型とストレージ](../build/types-and-storage.md)