---
title: リソース コンパイラ エラー RW2001 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW2001
dev_langs:
- C++
helpviewer_keywords:
- RW2001
ms.assetid: 963bdc7d-6ebe-4378-8bbc-47dfcf5d330c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 077260b615d0a5adf32278d8857df5b8f74b7e5f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33321101"
---
# <a name="resource-compiler-error-rw2001"></a>リソース コンパイラ エラー RW2001
プリプロセス済みの RC ファイルに無効なディレクティブ  
  
 RC ファイルが含まれています、 **#pragma**ディレクティブです。  
  
 使用して、 **#ifndef**プリプロセッサ ディレクティブの中で、 **RC_INVOKED**リソース コンパイラのインクルード ファイルを処理する際に定義する定数。 場所、 **#pragma**されていないコードのブロックの内側ディレクティブ処理時に、 **RC_INVOKED**定数が定義されています。 C と C++ コンパイラでのみ、リソース コンパイラではなく、ブロック内のコードが処理されます。 次のサンプル コードは、この手法を示します。  
  
```  
#ifndef RC_INVOKED  
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler  
#endif  
```  
  
 **#Pragma**プリプロセッサ ディレクティブ意味がない、します。RC ファイルです。 **#Include**プリプロセッサ ディレクティブで頻繁に使用します。ヘッダー ファイル (プロジェクト ベースのカスタム ヘッダー ファイルまたはその製品のいずれかの Microsoft によって提供される標準ヘッダー ファイル) を含める RC ファイルです。 これらのいくつかのインクルード ファイルが含まれて、 **#pragma**ディレクティブです。 ヘッダー ファイルが 1 つまたは複数の他のヘッダー ファイル、問題のあるを格納しているファイルを含めることができますので **#pragma**ディレクティブをすぐに判断できない可能性があります。  
  
 **#Ifndef RC_INVOKED**プロジェクト ベースのヘッダー ファイル内のヘッダー ファイルを含む方法を制御できます。