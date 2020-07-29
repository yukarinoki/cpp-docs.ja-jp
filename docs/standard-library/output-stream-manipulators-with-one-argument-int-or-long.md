---
title: 1 つの引数 (int または long) を使用する出力ストリーム マニピュレーター
ms.date: 11/04/2016
helpviewer_keywords:
- output streams, int or long argument manipulators
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
ms.openlocfilehash: 203797eef95e3dab0c079e35baefcea99c3b966d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217663"
---
# <a name="output-stream-manipulators-with-one-argument-int-or-long"></a>1 つの引数 (int または long) を使用する出力ストリーム マニピュレーター

iostream クラス ライブラリには、パラメーター化したマニピュレーターを作成するためのマクロ セットが用意されています。 1つの **`int`** 引数または引数を持つマニピュレーター **`long`** は特殊なケースです。 1つまたは複数の引数 (など) を受け入れる出力ストリームマニピュレーターを作成するには、 **`int`** **`long`** `setw` で定義されている _Smanip マクロを使用する必要があり \<iomanip> ます。 次の例では、指定した数の空白をストリームに挿入する `fillblank` マニピュレーターを定義します。

## <a name="example"></a>例

```cpp
// output_stream_manip.cpp
// compile with: /GR /EHsc
#include <iostream>
#include <iomanip>
using namespace std;

void fb( ios_base& os, int l )
{
   ostream *pos = dynamic_cast<ostream*>(&os);
   if (pos)
   {
      for( int i=0; i < l; i++ )
      (*pos) << ' ';
   };
}

_Smanip<int>
   __cdecl fillblank(int no)
   {
   return (_Smanip<int>(&fb, no));
   }

int main( )
{
   cout << "10 blanks follow" << fillblank( 10 ) << ".\n";
}
```

## <a name="see-also"></a>関連項目

[引数を使用したカスタムマニピュレーター](../standard-library/custom-manipulators-with-arguments.md)
