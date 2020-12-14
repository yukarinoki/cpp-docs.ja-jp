---
description: 詳細については、「バッファリングの影響」を参照してください。
title: バッファリングの効果
ms.date: 11/04/2016
helpviewer_keywords:
- buffers, effects of buffering
- buffering, effects of
ms.assetid: 5d544812-e95e-4f28-b15a-edef3f3414fd
ms.openlocfilehash: dc46a5a7a390250be1872f9264235e133b9f58ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232721"
---
# <a name="effects-of-buffering"></a>バッファリングの効果

次に、バッファリングの効果を示す例を示します。 `please wait`を出力して 5 秒待ってから先に進むプログラムを想定することができますが、 必ずしもそのとおりに動作するとは限りません。これは、出力がバッファリングされるためです。

```cpp
// effects_buffering.cpp
// compile with: /EHsc
#include <iostream>
#include <time.h>
using namespace std;

int main( )
{
   time_t tm = time( NULL ) + 5;
   cout << "Please wait...";
   while ( time( NULL ) < tm )
      ;
   cout << "\nAll done" << endl;
}
```

プログラムを論理的に動作させるには、メッセージが表示されたときに `cout` オブジェクトがそれ自体を空にする必要があります。 `ostream` オブジェクトをフラッシュするには、それを `flush` マニピュレーターに送信します。

```cpp
cout <<"Please wait..." <<flush;
```

この手順ではバッファーがフラッシュされるため、必ず待機の前にメッセージが出力されます。 また、 `endl` マニピュレーターを使用して、バッファーをフラッシュし、キャリッジリターンラインフィードを出力します。または、オブジェクトを使用することもでき `cin` ます。 通常、このオブジェクト (および `cerr` または `clog` オブジェクト) は `cout` オブジェクトに関連付けられています。 そのため、 `cin` (あるいは `cerr` または `clog` オブジェクト) を使用すると、 `cout` オブジェクトがフラッシュされます。

## <a name="see-also"></a>関連項目

[出力ストリーム](../standard-library/output-streams.md)
