---
title: リソース コンパイラ エラー RW2001 |Microsoft Docs
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
ms.openlocfilehash: f401ce7c9a96cfeecf195b8872a704b8b1291939
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114983"
---
# <a name="resource-compiler-error-rw2001"></a>リソース コンパイラ エラー RW2001

前処理済みの RC ファイルに無効なディレクティブ

RC ファイルが含まれています、 **#pragma**ディレクティブ。

使用して、 **#ifndef**プリプロセッサ ディレクティブ、 **RC_INVOKED**インクルード ファイルを処理する際、リソース コンパイラを定義する定数。 場所、 **#pragma**ディレクティブでないコードのブロック内で処理されるときに、 **RC_INVOKED**定数が定義されます。 C と C++ コンパイラでのみ、リソース コンパイラではなく、ブロック内のコードが処理されます。 次のサンプル コードでは、この手法を示します。

```
#ifndef RC_INVOKED
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler
#endif
```

**#Pragma**プリプロセッサ ディレクティブ意味がない、です。RC ファイルです。 **#Include**プリプロセッサ ディレクティブで頻繁に使用します。ヘッダー ファイル (プロジェクト ベースのカスタム ヘッダー ファイルまたはその製品のいずれかで、Microsoft によって提供される標準のヘッダー ファイル) を含める RC ファイルです。 これらのいくつかのインクルード ファイルが含まれて、 **#pragma**ディレクティブ。 ヘッダー ファイルは、1 つまたは複数の他のヘッダー ファイル、問題のあるを含むファイルを含めることができますので **#pragma**ディレクティブを簡単にすぐにできない可能性があります。

**#Ifndef RC_INVOKED**プロジェクト ベースのヘッダー ファイル内のヘッダー ファイルなどの手法を制御できます。