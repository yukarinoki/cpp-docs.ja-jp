---
title: _ _ll_lshift |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __ll_lshift_cpp
- __ll_lshift
dev_langs:
- C++
helpviewer_keywords:
- ll_lshift intrinsic
- __ll_lshift intrinsic
ms.assetid: fe98f733-426d-44b3-8f24-5d0d6d44bd94
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 364ad39bfe47ff04c4a1eefb52b32ed4bddb7809
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42539089"
---
# <a name="lllshift"></a>__ll_lshift
**Microsoft 固有の仕様**  
  
 指定した 64 ビット値が指定されたビット数だけ左にシフトします。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned __int64 __ll_lshift(  
   unsigned __int64 Mask,  
   int nBit  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `Mask`  
 左にシフトする 64 ビット整数値。  
  
 [入力] `nBit`  
 シフトするビット数。  
  
## <a name="return-value"></a>戻り値  
 マスクを左にシフト`nBit`ビット。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__ll_lshift`|x86、x64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>Remarks  
 64 ビット アーキテクチャを使用して、プログラムをコンパイルするかどうかと`nBit`63 を超えるにシフトするビットの数が`nBit`モジュロ 64 です。 32 ビット アーキテクチャを使用して、プログラムをコンパイルするかどうかと`nBit`31 より大きいにシフトするビットの数が`nBit`32 剰余。  
  
 `ll`名前では、操作であるを示します。 `long long` (`__int64`)。  
  
## <a name="example"></a>例  
  
```  
// ll_lshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ll_lshift)  
  
int main()  
{  
   unsigned __int64 Mask = 0x100;  
   int nBit = 8;  
   Mask = __ll_lshift(Mask, nBit);  
   cout << hex << Mask << endl;  
}  
```  
  
## <a name="output"></a>出力  
  
```  
10000  
```  
  
 **注**左シフト演算の符号なしのバージョンはありません。 これは、ため`__ll_lshift`既に署名されていない入力パラメーターを使用します。 右 shift キーを押しとは異なりはありません左 shift キーを押しへのサインオンのため、結果の最下位ビットは常にシフトした値の符号に関係なく 0 に設定します。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__ll_rshift](../intrinsics/ll-rshift.md)   
 [__ull_rshift](../intrinsics/ull-rshift.md)   
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)