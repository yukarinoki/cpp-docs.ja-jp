---
title: スカラー型 |Microsoft ドキュメント
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
ms.openlocfilehash: 5490bb33cafd8d2942e434ab9c50e34441506463
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32381172"
---
# <a name="scalar-types"></a>スカラー型
データへのアクセスは、どのように配置されてによって生じることができます、データが、パフォーマンスが失われる (やさまざまな理由) を回避する自然な境界に合わせて調整することをお勧めします。 列挙型が定数の整数であり、32 ビット整数値として扱われます。 次の表の種類の定義と推奨される記憶域を次のアラインメント値を使用して配置に関連します。  
  
-   バイトの 8 ビット  
  
-   Word の 16 ビット  
  
-   ダブル ワード - 32 ビット  
  
-   クアッド ワード - 64 ビット  
  
-   オクタワード - 128 ビット  
  
|||||  
|-|-|-|-|  
|スカラー型|C データ型|ストレージ サイズ (バイト単位)|推奨される配置|  
|**INT8**|`char`|1|Byte|  
|**UINT8**|`unsigned char`|1|Byte|  
|**INT16**|**short**|2|Word|  
|**UINT16**|**unsigned short**|2|Word|  
|**INT32**|**int、long**|4|ダブルワード|  
|**UINT32**|**符号なし int、unsigned long**|4|ダブルワード|  
|**INT64**|`__int64`|8|Quadword|  
|**UINT64**|**unsigned __int64**|8|Quadword|  
|**FP32 (1 つの有効桁数)**|**float**|4|ダブルワード|  
|**FP64 (有効桁数を 2 つ)**|**double**|8|Quadword|  
|**ポインター**|**\***|8|Quadword|  
|`__m64`|**構造体 _ _m64**|8|Quadword|  
|`__m128`|**_ _m128 の構造体**|16|Octaword|  
  
## <a name="see-also"></a>関連項目  
 [型とストレージ](../build/types-and-storage.md)