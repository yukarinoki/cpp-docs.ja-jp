---
title: _ _popcnt16、_ _popcnt、_ _popcnt64 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __popcnt64
- __popcnt
- __popcnt16
dev_langs:
- C++
helpviewer_keywords:
- popcnt instruction
- __popcnt16
- __popcnt64
- __popcnt
ms.assetid: e525b236-adc8-42df-9b9b-8b7d8c245d3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a639091bd7c5c263a3f09067858cd0fe4ac631cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33329197"
---
# <a name="popcnt16-popcnt-popcnt64"></a>__popcnt16、__popcnt、__popcnt64
**Microsoft 固有の仕様**  
  
 1 つの数をカウント、16、32 ビットまたは 64 バイトの符号なし整数のビット (カタログ作成数)。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned short __popcnt16(  
   unsigned short value  
);  
unsigned int __popcnt(  
   unsigned int value  
);  
unsigned __int64 __popcnt64(  
   unsigned __int64 value  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `value`  
 16、32 ビットまたは 64 ビット符号なし整数のビットの数を選びました。  
  
## <a name="return-value"></a>戻り値  
 1 つのビット数、`value`パラメーター。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__popcnt16`|高度なビット操作|  
|`__popcnt`|高度なビット操作|  
|`__popcnt64`|64 ビット モードでの高度なビット操作します。|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 これらの組み込みの各を生成、`popcnt`命令します。  値のサイズを`popcnt`命令は、その引数のサイズと同じを返します。  32 ビット モードではありません。 64 ビットの汎用レジスタ、したがっていいえ 64 ビット`popcnt`です。  
  
 ハードウェア サポートの決定に、`popcnt`命令を呼び出し、`__cpuid`で組み込み`InfoType=0x00000001`のビット 23 をチェックし、`CPUInfo[2] (ECX)`です。 このビットは、それ以外の場合、命令がサポートされている場合は 1 と 0 です。 かどうかはコードを実行するを使用するこの組み込みをサポートしていないハードウェア、`popcnt`命令、結果は予測できません。  
  
## <a name="example"></a>例  
  
```  
#include <iostream>   
#include <intrin.h>   
using namespace std;   
  
int main()   
{  
  unsigned short us[3] = {0, 0xFF, 0xFFFF};  
  unsigned short usr;  
  unsigned int   ui[4] = {0, 0xFF, 0xFFFF, 0xFFFFFFFF};  
  unsigned int   uir;  
  
  for (int i=0; i<3; i++) {  
    usr = __popcnt16(us[i]);  
    cout << "__popcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;  
  }  
  
  for (int i=0; i<4; i++) {  
    uir = __popcnt(ui[i]);  
    cout << "__popcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;  
  }  
}  
  
```  
  
```Output  
__popcnt16(0x0) = 0  
__popcnt16(0xff) = 8  
__popcnt16(0xffff) = 16  
__popcnt(0x0) = 0  
__popcnt(0xff) = 8  
__popcnt(0xffff) = 16  
__popcnt(0xffffffff) = 32  
```  
  
**Microsoft 固有の仕様はここまで**  
 高度なマイクロ デバイス, Inc. によって copyright 2007All rights reserved. 高度なマイクロ デバイス, Inc. のアクセス許可を持つ再現  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
