---
title: 左 shift キーおよび右シフト演算子 (&gt; &gt;と&lt; &lt;) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- <<
- '>>'
dev_langs:
- C++
helpviewer_keywords:
- << operator [C++], with specific objects
- left shift operators [C++]
- right shift operators [C++]
- bitwise-shift operators [C++]
- '>> operator'
- shift operators [C++]
- operators [C++], shift
ms.assetid: 25fa0cbb-5fdd-4657-8745-b35f7d8f1606
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0d8835d096575f3f7a9d50c7be26fa435e5d6bcd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32422398"
---
# <a name="left-shift-and-right-shift-operators-gtgt-and-ltlt"></a>左 shift キーおよび右シフト演算子 (&gt; &gt;と&lt; &lt;)
ビット処理シフト演算子は右シフト演算子 (>>) のビットを移動する*shift 式*、右に、左シフト演算子 (<<) のビットを移動する*shift 式*左側にします。 <sup>1</sup>  
  
## <a name="syntax"></a>構文  
  
> *shift キーを押し式* `<<` *式 additive*  
> *shift キーを押し式* `>>` *式 additive*  
  
## <a name="remarks"></a>コメント  
  
> [!IMPORTANT]
> 次の説明と例は x86 および x64 アーキテクチャ用 Windows で有効です。 左シフト演算子と右シフト演算子の実装は ARM デバイス用 Windows RT では大きく異なります。 詳細については、の「シフト演算子」セクションを参照して、 [Hello ARM](http://blogs.msdn.com/b/vcblog/archive/2012/10/25/hello-arm-exploring-undefined-unspecified-and-implementation-defined-behavior-in-c.aspx)ブログの投稿。  
  
## <a name="left-shifts"></a>左シフト  
 左シフト演算子でのビットが*shift 式*で指定された位置数だけ左にシフトする*式 additive*です。 シフト演算により空いたビット位置はゼロで埋められます。 左シフトは論理シフトです (符号ビットを含めてシフトし、溢れたビットは捨てます)。 ビットごとのシフトの種類の詳細については、次を参照してください。[ビットごとのシフト](http://en.wikipedia.org/wiki/Bitwise_shift)です。  
  
 次の例では、符号なし数値を使用した左シフト演算を示しています。 値をビットセットとして表すことでビットがどうなるかを示しています。 詳細については、次を参照してください。 [bitset クラス](../standard-library/bitset-class.md)です。  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    unsigned short short1 = 4;      
    bitset<16> bitset1{short1};   // the bitset representation of 4  
    cout << bitset1 << endl;  // 0000000000000100  
  
    unsigned short short2 = short1 << 1;     // 4 left-shifted by 1 = 8  
    bitset<16> bitset2{short2};  
    cout << bitset2 << endl;  // 0000000000001000  
  
    unsigned short short3 = short1 << 2;     // 4 left-shifted by 2 = 16  
    bitset<16> bitset3{short3};  
    cout << bitset3 << endl;  // 0000000000010000  
}  
  
```  
  
 符号付き数値をシフトして符号ビットが影響を受ける場合、結果は未定義です。 次の例では、符号ビットの位置まで 1 ビット左にシフトしたときに Visual C でどうなるかを示しています。  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    short short1 = 16384;      
    bitset<16> bitset1{short2};  
    cout << bitset1 << endl;  // 0100000000000000   
  
    short short3 = short1 << 1;  
    bitset<16> bitset3{short3};  // 16384 left-shifted by 1 = -32768  
    cout << bitset3 << endl;  // 100000000000000  
  
    short short4 = short1 << 14;  
    bitset<16> bitset4{short4};  // 4 left-shifted by 14 = 0  
    cout << bitset4 << endl;  // 000000000000000    
}  
```  
  
## <a name="right-shifts"></a>右シフト  
 右シフト演算子の結果のビット パターン*shift 式*で指定された位置数だけ右にシフトする*式 additive*です。 符号なし数値の場合、シフト演算により空いたビット位置はゼロで埋められます。 符号付き数値の場合、その空いたビット位置は符号ビットで埋められます。 つまり、数値が正である場合は 0 を使用し、数値が負である場合は 1 を使用します。  
  
> [!IMPORTANT]
> 符号付きの負の数値の右シフトの結果は実装に依存します。 Visual C++ では空いたビット位置は符号ビットで埋められますが、他の実装でも同様であるとは限りません。  
  
 次の例では、符号なし数値を使用した左シフト演算を示しています。  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    unsigned short short11 = 1024;  
    bitset<16> bitset11{short11};  
    cout << bitset11 << endl;     // 0000010000000000  
  
    unsigned short short12 = short11 >> 1;  // 512  
    bitset<16> bitset12{short12};  
    cout << bitset12 << endl;     // 0000001000000000  
  
    unsigned short short13 = short11 >> 10;  // 1  
    bitset<16> bitset13{short13};  
    cout << bitset13 << endl;     // 0000000000000001  
  
    unsigned short short14 = short11 >> 11;  // 0  
    bitset<16> bitset14{short14};  
    cout << bitset14 << endl;     // 0000000000000000}  
}  
```  
  
 次の例では、正の符号付き数値を使用した右シフト演算を示しています。  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    short short1 = 1024;  
    bitset<16> bitset1{short1};  
    cout << bitset1 << endl;     // 0000010000000000  
  
    short short2 = short1 >> 1;  // 512  
    bitset<16> bitset2{short2};  
    cout << bitset2 << endl;     // 0000001000000000  
  
    short short3 = short1 >> 11;  // 0  
    bitset<16> bitset3{short3};     
    cout << bitset3 << endl;     // 0000000000000000  
}  
```  
  
 次の例では、負の符号付き整数を使用した右シフト演算を示しています。  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    short neg1 = -16;  
    bitset<16> bn1{neg1};  
    cout << bn1 << endl;  // 1111111111110000  
  
    short neg2 = neg1 >> 1; // -8  
    bitset<16> bn2{neg2};  
    cout << bn2 << endl;  // 1111111111111000  
  
    short neg3 = neg1 >> 2; // -4  
    bitset<16> bn3{neg3};  
    cout << bn3 << endl;  // 1111111111111100  
  
    short neg4 = neg1 >> 4; // -1  
    bitset<16> bn4{neg4};      
    cout << bn4 << endl;  // 1111111111111111  
  
    short neg5 = neg1 >> 5; // -1   
    bitset<16> bn5{neg5};      
    cout << bn5 << endl;  // 1111111111111111  
}  
```  
  
## <a name="shifts-and-promotions"></a>シフトと昇格  
 シフト演算子の両側の式は整数型であることが必要です。 説明する規則に従って整数の上位変換が実行されます[標準変換](standard-conversions.md)です。 結果の型は、昇格の種類と同じ*shift 式*です。  
  
 次の例では、`char` 型の変数が `int` に昇格しています。  
  
```cpp  
#include <iostream>  
#include <typeinfo>  
  
using namespace std;  
  
int main() {  
    char char1 = 'a';  
  
    auto promoted1 = char1 << 1;   // 194  
    cout << typeid(promoted1).name() << endl;  // int  
  
    auto promoted2 = char1 << 10;  // 99328  
    cout << typeid(promoted2).name() << endl;  // int  
}  
```  
  
## <a name="additional-details"></a>追加の詳細情報  
 シフト演算の結果が定義されていない場合は*式 additive*が負の値または*式 additive*がより大きいか、(昇格) 内のビット数と等しく*shift キーを押し式*です。 場合シフト演算は実行されません*式 additive*は 0 です。  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    unsigned int int1 = 4;  
    bitset<32> b1{int1};  
    cout << b1 << endl;    // 00000000000000000000000000000100  
  
    unsigned int int2 = int1 << -3;  // C4293: '<<' : shift count negative or too big, undefined behavior  
    unsigned int int3 = int1 >> -3;  // C4293: '>>' : shift count negative or too big, undefined behavior  
  
    unsigned int int4 = int1 << 32;  // C4293: '<<' : shift count negative or too big, undefined behavior  
  
    unsigned int int5 = int1 >> 32;  // C4293: '>>' : shift count negative or too big, undefined behavior  
  
    unsigned int int6 = int1 << 0;  
    bitset<32> b6{int6};  
    cout << b6 << endl;    // 00000000000000000000000000000100 (no change)}  
}  
```  
  
## <a name="footnotes"></a>脚注  
 1、ここでは、c++ 11 ISO 仕様 (INCITS/ISO/IEC 14882-2011[2012])、5.8.2 節と 5.8.3 でのシフト演算子の説明。  
  
 値**E1 << E2**は**E1**左にシフトした**E2**ビット; 空いたビットはゼロで埋められます。 場合**E1**符号なしの型が、結果の値が**E1 × 2**<sup>**E2**</sup>、剰余で表現できる最大値より 1 削減結果の型。 それ以外の場合**E1**は、符号付きの型と非負の値、および**E1 × 2**<sup>**E2** </sup>は対応する符号なしの型で表現できます。結果の型のその値、結果型に変換は結果として得られる値です。それ以外の場合、動作は定義されません。  
  
 値**E1 >> E2**は**E1**右にシフトした**E2**ビット位置。 場合**E1**符号なしの型を持つ場合、または**E1**符号付きの型と、負でない値を持つ、結果の値の商の整数部分は、 **E1/2** <sup>**E2**</sup>です。 場合**E1**符号付きの型と負の値には、結果の値は実装定義します。  
  
## <a name="see-also"></a>関連項目  
 [二項演算子を含む式](../cpp/expressions-with-binary-operators.md)   
 [C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)