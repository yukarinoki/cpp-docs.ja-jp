---
title: X86 との競合コンパイラ |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8e47f0d3-afe0-42d9-9efa-de239ddd3a05
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7f01e65adfb42a5fb3361e75ce34060f7dc1b9f9
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709673"
---
# <a name="conflicts-with-the-x86-compiler"></a>x86 コンパイラとの競合

4 バイトが自動的に整列していません、スタック、x86 を使用する場合よりも大きいデータ型をコンパイラにアプリケーションをコンパイルします。 のアーキテクチャを x86 コンパイラでは、4 バイトで、たとえば、64 ビットの整数よりも大きな、4 バイトのアラインされたスタックが 8 バイトのアドレスに自動的に配置することはできません。

アラインされていないデータの操作では、2 つの影響を与えます。

- アラインされていない場所へのアクセスに配置された場所にアクセスするよりも長い時間がかかる場合があります。

- インタロックされた操作では、アラインされていない場所を使用できません。

複数の厳密なアラインメントが必要な場合を使用して、`__declspec(align(N)) on your variable declarations`します。 動的に、仕様に合わせて、スタックに揃えをコンパイラに対応します。 ただし、実行時にスタックを動的に調整すると、アプリケーションの実行速度が遅くが発生する可能性があります。

## <a name="see-also"></a>関連項目

[型とストレージ](../build/types-and-storage.md)<br/>
[align](../cpp/align-cpp.md)