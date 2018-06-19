---
title: 1 つの引数 (int または long) を使用する出力ストリーム マニピュレーター | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- output streams, int or long argument manipulators
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f3238ffcbd03f40c6eac0423d0212a65719fb33d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853074"
---
# <a name="output-stream-manipulators-with-one-argument-int-or-long"></a>1 つの引数 (int または long) を使用する出力ストリーム マニピュレーター

iostream クラス ライブラリには、パラメーター化したマニピュレーターを作成するためのマクロ セットが用意されています。 単一の `int` 引数または `long` 引数のみを取るマニピュレーターは特殊なケースです。 単一の `int` 引数または `long` 引数を受け取る出力ストリーム マニピュレーター (`setw` など) を作成するには、\<iomanip> で定義される _Smanip マクロを使用する必要があります。 次の例では、指定した数の空白をストリームに挿入する `fillblank` マニピュレーターを定義します。

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

[引数を使用するカスタム マニピュレーター](../standard-library/custom-manipulators-with-arguments.md)<br/>
