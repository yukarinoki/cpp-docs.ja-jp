---
title: リソース コンパイラ エラー RC2101 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2101
dev_langs:
- C++
helpviewer_keywords:
- RC2101
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b07f6211e1cc36bd471b04126e724e42eb610641
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33330818"
---
# <a name="resource-compiler-error-rc2101"></a>リソース コンパイラ エラー RC2101
プリプロセス済みの RC ファイルに無効なディレクティブ  
  
 リソース コンパイラのファイルが含まれています、 **#pragma**ディレクティブです。  
  
 使用して、 **#ifndef**プリプロセッサ ディレクティブの中でインクルード ファイルを処理する際に、リソース コンパイラが定義される RC_INVOKED 定数。 場所、 **#pragma** RC_INVOKED 定数が定義されている場合は処理されていないコードのブロックの内側ディレクティブです。 C と C++ コンパイラでのみ、リソース コンパイラではなく、ブロック内のコードが処理されます。 次のサンプル コードは、この手法を示します。  
  
```  
#ifndef RC_INVOKED  
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler  
#endif  
```  
  
 **#Pragma**プリプロセッサ ディレクティブ意味がない、します。RC ファイルです。 **#Include**プリプロセッサ ディレクティブで頻繁に使用します。ヘッダー ファイル (プロジェクト ベースのカスタム ヘッダー ファイルまたはその製品のいずれかの Microsoft によって提供される標準ヘッダー ファイル) を含める RC ファイルです。 これらのいくつかのインクルード ファイルが含まれて、 **#pragma**ディレクティブです。 ヘッダー ファイルが 1 つまたは複数の他のヘッダー ファイル、問題のあるを格納しているファイルを含めることができますので **#pragma**ディレクティブをすぐに判断できない可能性があります。  
  
 **#Ifndef**プロジェクト ベースのヘッダー ファイル内のヘッダー ファイルを含む RC_INVOKED 方法を制御できます。