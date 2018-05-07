---
title: _BitScanForward、_BitScanForward64 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _BitScanForward
- _BitScanForward_cpp
- _BitScanForward64_cpp
- _BitScanForward64
dev_langs:
- C++
helpviewer_keywords:
- _BitScanForward intrinsic
- bsf instruction
- BitScanForward intrinsic
ms.assetid: 405e60fb-0815-42a7-9b02-6fc035122203
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad785bb7789156a2f5105e89a493877fb30c2f3e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="bitscanforward-bitscanforward64"></a>_BitScanForward、_BitScanForward64
**Microsoft 固有の仕様**  
  
 マスク データの最下位ビット (LSB) から最上位ビット (MSB) に向かって設定済みビット (1) を検索します。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned char _BitScanForward(  
   unsigned long * Index,  
   unsigned long Mask  
);  
unsigned char _BitScanForward64(  
   unsigned long * Index,  
   unsigned __int64 Mask  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `Index`  
 最初に見つかった設定済みビット (1) のビット位置が読み込まれます。  
  
 [入力] `Mask`  
 検索する 32 ビットまたは 64 ビットの値。  
  
## <a name="return-value"></a>戻り値  
 マスクが 0 の場合は 0。それ以外の場合は 0 以外。  
  
## <a name="remarks"></a>コメント  
 設定済みビットが見つかった場合は、最初に見つかった設定済みビットのビット位置が最初のパラメーターで返されます。 設定済みビットが見つからない場合は 0 が返されます。それ以外の場合は 1 が返されます。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`_BitScanForward`|x86、ARM、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_BitScanForward64`|ARM、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="example"></a>例  
  
```  
// BitScanForward.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(_BitScanForward)  
  
int main()  
{  
   unsigned long mask = 0x1000;  
   unsigned long index;  
   unsigned char isNonzero;  
  
   cout << "Enter a positive integer as the mask: " << flush;  
   cin >> mask;  
   isNonzero = _BitScanForward(&index, mask);  
   if (isNonzero)  
   {  
      cout << "Mask: " << mask << " Index: " << index << endl;  
   }  
   else  
   {  
      cout << "No set bits found.  Mask is zero." << endl;  
   }  
}  
```  
  
## <a name="input"></a>入力  
  
```  
12  
```  
  
## <a name="sample-output"></a>出力例  
  
```  
Enter a positive integer as the mask:   
Mask: 12 Index: 2  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)