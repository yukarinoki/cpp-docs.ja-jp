---
title: 整数の制限 |Microsoft Docs
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- integral limits
- limits, integer
- limits.h header file
- integer limits
ms.assetid: 6922bdbf-0f49-443b-bc03-ee182e4cbd57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b9a516ef366952f9d55e16891dfcb7bb81fac7e
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406020"
---
# <a name="integer-limits"></a>整数の制限

**Microsoft 固有の仕様**

次の表に、整数型の制限を示します。 これらの制限も、標準ヘッダー ファイルの < limits.h > で定義されます。

## <a name="limits-on-integer-constants"></a>整数定数の制限

|定数|説明|[値]|
|--------------|-------------|-----------|
|CHAR_BIT|ビット フィールドではない最小変数のビット数。|8|
|SCHAR_MIN|**signed char** 型変数の最小値。|-128|
|SCHAR_MAX|**signed char** 型変数の最大値。|127|
|UCHAR_MAX|**unsigned char** 型変数の最大値。|255 (0xff)|
|CHAR_MIN|**char** 型変数の最小値。|-128 (/J オプションが使用される場合は 0)|
|CHAR_MAX|**char** 型変数の最小値。|-127 (/J オプションが使用される場合は 255)|
|MB_LEN_MAX|多文字定数の最大バイト数。|5|
|SHRT_MIN|**short** 型変数の最小値。|-32768|
|SHRT_MAX|**short** 型変数の最大値。|32767|
|USHRT_MAX|**unsigned short** 型変数の最大値。|65535 (0xffff)|
|INT_MIN|**int** 型変数の最小値。|-2147483648|
|INT_MAX|**int** 型変数の最大値。|2147483647|
|UINT_MAX|**unsigned int** 型変数の最大値。|4294967295 (0xffffffff)|
|LONG_MIN|**long** 型変数の最小値。|-2147483648|
|LONG_MAX|**long** 型変数の最大値。|2147483647|
|ULONG_MAX|**unsigned long** 型変数の最大値。|4294967295 (0xffffffff)|
|LLONG_MIN|型の変数の最小値**long**|-9223372036854775808|
|LLONG_MAX|型の変数の最大値**long**|9223372036854775807|
|ULLONG_MAX|型の変数の最大値**unsigned long long 型**|18446744073709551615 (0xffffffffffffffff)|

値が最大の整数表現を超えると、Microsoft コンパイラでエラーが生成されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目
 [浮動小数点の制限](../cpp/floating-limits.md)  