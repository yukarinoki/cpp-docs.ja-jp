---
description: 詳細については、「インラインアセンブリの利点」を参照してください。
title: インライン アセンブラーの長所
ms.date: 08/30/2018
helpviewer_keywords:
- assembler [C++], advantages
- inline assembly [C++], about inline assembly
- inline assembly [C++], using
ms.assetid: 94364d97-faa7-4bdf-8473-570956986c51
ms.openlocfilehash: 066824a4ad63641f33712219dd8364b0edf7259b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118070"
---
# <a name="advantages-of-inline-assembly"></a>インライン アセンブラーの長所

**Microsoft 固有の仕様**

インライン アセンブラーは別のアセンブリとリンクの手順を必要としないので、別のアセンブラーより便利です。 インライン アセンブラー コードでは、スコープ内にある C 変数や関数名を使用できるので、プログラムの C コードと簡単に統合できます。 アセンブリコードは C または C++ のステートメントを使用してインラインで混在させることができるため、C または C++ では煩雑または不可能なタスクを実行できます。

インラインアセンブリの使用方法は次のとおりです。

- アセンブリ言語での関数の記述。

- コードの高速で重要なセクションをスポット最適化します。

- デバイスドライバーに直接ハードウェアアクセスを行う。

- "生の" 呼び出しのプロローグとエピローグコードを記述する。

インラインアセンブリは、特別な用途のツールです。 アプリケーションを別のコンピューターに移植する場合は、コンピューター固有のコードを別のモジュールに配置することをお勧めします。 インラインアセンブラーでは、Microsoft マクロアセンブラーの (MASM) マクロとデータディレクティブがすべてサポートされていないため、このようなモジュールには MASM を使用する方が便利な場合があります。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[インラインアセンブラー](../../assembler/inline/inline-assembler.md)<br/>
