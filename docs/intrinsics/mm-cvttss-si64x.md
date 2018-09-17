---
title: _mm_cvttss_si64x |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_cvttss_si64x
dev_langs:
- C++
helpviewer_keywords:
- _mm_cvttss_si64x intrinsic
- cvttss2si instruction
ms.assetid: f9a3fd07-5bd8-4758-8744-6315c082cf87
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d1d3e77dfc89fb67c467582c0ed7981ffae8022
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706343"
---
# <a name="mmcvttsssi64x"></a>_mm_cvttss_si64x
**Microsoft 固有の仕様**  
  
 出力拡張 x64 バージョンの 64 ビットの整数に切り捨て単精度浮動小数点数に変換 (`cvttss2si`) 命令。  
  
## <a name="syntax"></a>構文  
  
```  
__int64 _mm_cvttss_si64x(   
   __m128 value   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
*値*<br/>
[in]`__m128`単精度浮動小数点値を含む構造体。  
  
## <a name="return-value"></a>戻り値  
 最初の浮動小数点値の 64 ビット整数への変換の結果。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`_mm_cvttss_si64x`|X64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>Remarks  
 組み込みの異なる`_mm_cvtss_si64x`不正確な変換は、ゼロに向かって切り捨てられます。 その内のみです。 `__m128`構造体が、XMM レジスタを表す、生成された命令をシステム メモリに、XMM レジスタからデータを移動します。  
  
 このルーチンは、組み込みとしてのみ使用できます。  
  
## <a name="example"></a>例  
  
```  
// _mm_cvttss_si64x.cpp  
// processor: x64  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvttss_si64x)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    // _mm_load_ps requires an aligned buffer.  
    __declspec(align(16)) float af[4] = { 101.5, 200.75,  
                                          300.5, 400.5 };  
  
    // Load a with the floating point values.  
    // The values will be copied to the XMM registers.  
    a = _mm_load_ps(af);  
  
    // Extract the first element of a and convert to an integer  
    b = _mm_cvttss_si64x(a);  
  
    printf_s("%I64d\n", b);  
}  
```  
  
```Output  
101  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__m128](../cpp/m128.md)   
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)