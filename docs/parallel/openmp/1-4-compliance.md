---
title: 1.4 コンプライアンス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 662ad260-b9a1-43b7-b269-ef6ff0714e05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c1bde41491f456ff99b0cd0d1ccc8ab98508412
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687232"
---
# <a name="14-compliance"></a>1.4 準拠
OpenMP C と C++ API の実装は*OpenMP 準拠*かどうかを認識し、章 1、2、3、4、レイアウトとは、この仕様のすべての要素のセマンティクスを保持および付録 C A、B、D、E、および F情報は、目的でのみと仕様の一部ではないです。 API のサブセットのみを含む実装は、OpenMP 準拠ではありません。  
  
 OpenMP C および C++ API、実装でサポートされているベース言語拡張であります。 基本言語は、このドキュメントで言語コンストラクトまたは表示される拡張機能をサポートしない場合、OpenMP の実装をサポートするように必要はありません。  
  
 すべての C および C++ の標準ライブラリ関数および組み込み関数 (つまり、コンパイラが特定のナレッジには、関数) のスレッド セーフである必要があります。 並行領域内の別のスレッドでスレッド セーフである関数の非同期の使用には、未定義の動作は生成されません。 ただし、動作はありませんシリアル領域のものと同じです。 (ランダムな番号生成関数は、例を示します)。  
  
 OpenMP C と C++ API では、特定の動作は、ことを指定します*実装で定義します。* OpenMP に準拠した実装を定義し、このような場合は、その動作を文書化する必要があります。 参照してください[付録 E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md)、実装定義の動作の一覧については、97 のページです。