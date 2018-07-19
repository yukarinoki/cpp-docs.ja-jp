---
title: 戻り値 (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 53583524-b337-4228-a9c6-c9bf516babe8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec5097ab22ff82883117b6d224bce9c282ac9c8a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380322"
---
# <a name="return-values-c"></a>戻り値 (C++)
64 ビットに収まるスカラー戻り値は、RAX (__m64 型を含む) を通じて返されます。 非スカラー型の浮動小数点値、2 倍になり、およびなどのベクトルの型を含む[_ _m128](../cpp/m128.md)、 [_ _m128i](../cpp/m128i.md)、 [_ _m128d](../cpp/m128d.md) XMM0 で返されます。 RAX や XMM0 で返される値の未使用ビットの状態は未定義です。  
  
 ユーザー定義型は、グローバル関数や静的メンバー関数からの値で返すことができます。 RAX で値によって返すには、ユーザー定義型の長さが 1、2、4、8、16、32、または 64 ビットでなければなりません。ユーザー定義型のコンストラクター、デストラクター、またはコピー代入演算子ではなく、プライベートまたは保護された非静的データ メンバーではなく、参照型の非静的データ メンバーではなく、基底クラスではなく、仮想関数ではありません。これらの要件を満たさないデータ メンバーでもありません。 (これは、実質的には C++03 POD 型の定義です。 C++11 規格ではこの定義は変更されているので、このテストに `std::is_pod` を使うことはお勧めしません。)それ以外の場合は、呼び出し元が、メモリを割り当て、最初の引数として戻り値のポインターを渡す必要があります。 後続する引数は、引数 1 つ分だけ右にシフトされます。 RAX 内の呼び出し先は同じポインターを返す必要があります。  
  
 以下の例は、宣言を指定して関数に対してパラメーターと戻り値を渡す方法を示しています。  
  
## <a name="example-of-return-value-1---64-bit-result"></a>戻り値 1 ~ 64 ビットの結果の例  
  
```Output  
__int64 func1(int a, float b, int c, int d, int e);  
// Caller passes a in RCX, b in XMM1, c in R8, d in R9, e pushed on stack,  
// callee returns __int64 result in RAX.  
```  
  
## <a name="example-of-return-value-2---128-bit-result"></a>戻り値の 2 ~ 128 ビットの結果の例  
  
```Output  
__m128 func2(float a, double b, int c, __m64 d);   
// Caller passes a in XMM0, b in XMM1, c in R8, d in R9,   
// callee returns __m128 result in XMM0.  
```  
  
## <a name="example-of-return-value-3---user-type-result-by-pointer"></a>3 - ポインターによるユーザー型の結果の戻り値の例  
  
```Output  
struct Struct1 {  
   int j, k, l;    // Struct1 exceeds 64 bits.   
};  
Struct1 func3(int a, double b, int c, float d);   
// Caller allocates memory for Struct1 returned and passes pointer in RCX,   
// a in RDX, b in XMM2, c in R9, d pushed on the stack;   
// callee returns pointer to Struct1 result in RAX.  
```  
  
## <a name="example-of-return-value-4---user-type-result-by-value"></a>4 - 値によるユーザー型の結果の戻り値の例  
  
```Output  
struct Struct2 {  
   int j, k;    // Struct2 fits in 64 bits, and meets requirements for return by value.  
};  
Struct2 func4(int a, double b, int c, float d);   
// Caller passes a in RCX, b in XMM1, c in R8, and d in XMM3;   
// callee returns Struct2 result by value in RAX.  
```  
  
## <a name="see-also"></a>関連項目  
 [呼び出し規則](../build/calling-convention.md)