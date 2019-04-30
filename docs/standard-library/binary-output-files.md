---
title: バイナリ出力ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [C++], binary output files
- files [C++], binary output files
- binary data, binary output files
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
ms.openlocfilehash: 99445275a8f92622f451e8a88082dc2b28fb60b6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62414062"
---
# <a name="binary-output-files"></a>バイナリ出力ファイル

ストリームは本来、テキスト向けとして設計されており、既定の出力モードはテキストです。 テキスト モードでは、改行文字 (16 進数 10) は、キャリッジ リターンとラインフィード (16 ビットのみ) に展開されます。 この拡大は次のような問題を起こす可能性があります。

```cpp
// binary_output_files.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;
int iarray[2] = { 99, 10 };
int main( )
{
    ofstream os( "test.dat" );
    os.write( (char *) iarray, sizeof( iarray ) );
}
```

このプログラムでは、{ 99, 0, 10, 0 } というバイト シーケンスの出力を想定していたところ、{ 99, 0, 13, 10, 0 } が出力されます。バイナリ入力を要求するプログラムで問題が起こります。 文字が変換なしで書き込まれる、本来のバイナリ出力が必要であれば、[ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) コンストラクター オープンモード引数を利用し、バイナリ出力を指定できます。

```cpp
// binary_output_files2.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;
int iarray[2] = { 99, 10 };

int main()
{
   ofstream ofs ( "test.dat", ios_base::binary );

   // Exactly 8 bytes written
   ofs.write( (char*)&iarray[0], sizeof(int)*2 );
}
```

## <a name="see-also"></a>関連項目

[出力ストリーム](../standard-library/output-streams.md)<br/>
