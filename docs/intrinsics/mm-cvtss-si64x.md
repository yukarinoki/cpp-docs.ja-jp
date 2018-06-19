---
title: _mm_cvtss_si64x |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_cvtss_si64x
dev_langs:
- C++
helpviewer_keywords:
- cvtss2si intrinsic
- _mm_cvtss_si64x intrinsic
ms.assetid: c279aff2-ee29-4271-8829-3ec691bf7718
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 665c52fc0dd0645e25d3014cc28f9fdfba344e2d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332105"
---
# <a name="mmcvtsssi64x"></a>_mm_cvtss_si64x
**Microsoft 固有の仕様**  
  
 生成、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]変換スカラー単一単精度浮動小数点数の 64 ビットの整数に拡張バージョン (`cvtss2si`) 命令します。  
  
## <a name="syntax"></a>構文  
  
```  
__int64 _mm_cvtss_si64x(   
   __m128 value   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `value`  
 `__m128`浮動小数点値を含む構造体。  
  
## <a name="return-value"></a>戻り値  
 64 ビット整数の場合、最初の浮動小数点値の整数への変換の結果。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`_mm_cvtss_si64x`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 構造値の最初の要素が整数に変換され、返されます。 MXCSR で丸め制御ビットを使用して、丸め処理を決定します。 既定の丸めモードは、小数部が 0.5 である場合、偶数丸められる最も近い round です。 `__m128`構造は、この組み込みは、XMM レジスタの値は XMM レジスタを表すし、システム メモリに書き込みます。  
  
 このルーチンは、組み込みとしてのみ使用できます。  
  
## <a name="example"></a>例  
  
```  
// _mm_cvtss_si64x.cpp  
// processor: x64  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvtss_si64x)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    // _mm_load_ps requires an aligned buffer.  
    __declspec(align(16)) float af[4] =  
                           { 101.25, 200.75, 300.5, 400.5 };  
  
    // Load a with the floating point values.  
    // The values will be copied to the XMM registers.  
    a = _mm_load_ps(af);  
  
    // Extract the first element of a and convert to an integer  
    b = _mm_cvtss_si64x(a);  
  
    printf_s("%I64d\n", b);  
}  
```  
  
```Output  
101  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__m128d](../cpp/m128d.md)   
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)