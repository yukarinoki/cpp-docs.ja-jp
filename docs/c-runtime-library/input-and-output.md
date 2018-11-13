---
title: 入出力
ms.date: 11/04/2016
f1_keywords:
- c.io
helpviewer_keywords:
- input routines
- I/O [CRT]
- I/O routines
- I/O [CRT], routines
- output routines
ms.assetid: 1c177301-e341-4ca0-aedc-0a87fe1c75ae
ms.openlocfilehash: 26d527f7afad544b051a2ad765af09c430782083
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590386"
---
# <a name="input-and-output"></a>入出力

I/O 関数はファイルやデバイスとの間でデータの読み書きを行います。 ファイル I/O 操作は、テキスト モードまたはバイナリ モードで行われます。 Microsoft ランタイム ライブラリには、次の 3 つの種類の I/O 関数があります。

- [ストリーム入出力](../c-runtime-library/stream-i-o.md)関数は、データを個々の文字のストリームとして処理します。

- [下位入出力](../c-runtime-library/low-level-i-o.md)関数は、ストリーム入出力の操作より下位の操作に対してオペレーティング システムを直接呼び出します。

- [コンソール入出力とポート入出力](../c-runtime-library/console-and-port-i-o.md)関数は、コンソール () または入出力ポートに対して読み書きを直接実行します。

   > [!NOTE]
   > ストリーム関数はバッファーされ、下位入出力関数はバッファーされないため、これら 2 つの種類の関数には一般的に互換性がありません。 特定のファイルを処理するとき、ストリーム関数または下位入出力関数のいずれかを排他的に使用してください。

## <a name="see-also"></a>参照

[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)<br/>
