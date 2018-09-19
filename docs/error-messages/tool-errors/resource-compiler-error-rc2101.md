---
title: リソース コンパイラ エラー RC2101 |Microsoft Docs
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
ms.openlocfilehash: 196806e6d2767c889ae96d239af69113c542ba6c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034760"
---
# <a name="resource-compiler-error-rc2101"></a>リソース コンパイラ エラー RC2101

前処理済みの RC ファイルに無効なディレクティブ

リソース コンパイラのファイルが含まれています、 **#pragma**ディレクティブ。

使用して、 **#ifndef**インクルード ファイルを処理する際、リソース コンパイラを定義する RC_INVOKED 定数とプリプロセッサ ディレクティブです。 場所、 **#pragma** RC_INVOKED 定数が定義されている場合に処理されていないコードのブロック内のディレクティブ。 C と C++ コンパイラでのみ、リソース コンパイラではなく、ブロック内のコードが処理されます。 次のサンプル コードでは、この手法を示します。

```
#ifndef RC_INVOKED
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler
#endif
```

**#Pragma**プリプロセッサ ディレクティブ意味がない、です。RC ファイルです。 **#Include**プリプロセッサ ディレクティブで頻繁に使用します。ヘッダー ファイル (プロジェクト ベースのカスタム ヘッダー ファイルまたはその製品のいずれかで、Microsoft によって提供される標準のヘッダー ファイル) を含める RC ファイルです。 これらのいくつかのインクルード ファイルが含まれて、 **#pragma**ディレクティブ。 ヘッダー ファイルは、1 つまたは複数の他のヘッダー ファイル、問題のあるを含むファイルを含めることができますので **#pragma**ディレクティブを簡単にすぐにできない可能性があります。

**#Ifndef**プロジェクト ベースのヘッダー ファイル内のヘッダー ファイルを含む RC_INVOKED 手法を制御できます。