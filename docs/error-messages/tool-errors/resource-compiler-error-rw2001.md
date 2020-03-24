---
title: リソース コンパイラ エラー RW2001
ms.date: 11/04/2016
f1_keywords:
- RW2001
helpviewer_keywords:
- RW2001
ms.assetid: 963bdc7d-6ebe-4378-8bbc-47dfcf5d330c
ms.openlocfilehash: 900bfed9d57af0f6f5dd8fac19380bb7c382addc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190743"
---
# <a name="resource-compiler-error-rw2001"></a>リソース コンパイラ エラー RW2001

前処理される RC ファイルのディレクティブが無効です

RC ファイルには、 **#pragma**ディレクティブが含まれています。

**#Ifndef**プリプロセッサディレクティブは、インクルードファイルを処理するときにリソースコンパイラが定義する**RC_INVOKED**定数と共に使用します。 **#Pragma**ディレクティブを、 **RC_INVOKED**定数が定義されているときに処理されないコードブロック内に配置します。 ブロック内のコードは、リソースコンパイラによってC++ではなく、C/コンパイラによってのみ処理されます。 次のサンプルコードは、この手法を示しています。

```
#ifndef RC_INVOKED
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler
#endif
```

**#Pragma**プリプロセッサディレクティブは、に意味がありません。RC ファイル。 **#Include**プリプロセッサディレクティブは、で頻繁に使用されます。RC ファイルにヘッダーファイルが含まれています (プロジェクトベースのカスタムヘッダーファイル、または Microsoft によって提供される標準ヘッダーファイルを製品のいずれかと共に使用)。 これらのインクルードファイルには、 **#pragma**ディレクティブが含まれています。 ヘッダーファイルには、他の1つ以上のヘッダーファイルを含めることができるため、問題のある **#pragma**ディレクティブを含むファイルはすぐにはわからない可能性があります。

**#Ifndef RC_INVOKED**技法では、プロジェクトベースのヘッダーファイルにヘッダーファイルを含めるように制御できます。
