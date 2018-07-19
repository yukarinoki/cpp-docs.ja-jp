---
title: X86 と競合していますコンパイラ |Microsoft ドキュメント
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
ms.openlocfilehash: 7cd72de4922c297b4a230e0dc0fb606b56a2a473
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366914"
---
# <a name="conflicts-with-the-x86-compiler"></a>x86 コンパイラとの競合
4 バイトが自動的に整列していませんスタック、x86 を使用する場合より大きく、データ型、アプリケーションをコンパイルします。 コンパイラは、4 バイトのアラインされたスタック、たとえば、64 ビットの整数の 4 バイトよりも大きなは 8 バイトのアドレスを自動的にアラインことはできません、x86 のアーキテクチャです。  
  
 アライメントされていないデータの操作は、次の 2 つの影響を与えます。  
  
-   アライメントされていない場所にアクセスするアラインされた場所にアクセスする場合以外に長い時間がかかる場合があります。  
  
-   アライメントされていない場所は、インタロックされた操作では使用できません。  
  
 複数の厳密なアラインメントを必要とする場合を使用して`__declspec(align(N)) on your variable declarations`です。 これは、コンパイラで、仕様に合わせて、スタックを動的に調整します。 ただし、実行時に、スタックを動的に調整すると、アプリケーションの実行速度が遅くが発生する可能性があります。  
  
## <a name="see-also"></a>関連項目  
 [型とストレージ](../build/types-and-storage.md)   
 [align](../cpp/align-cpp.md)