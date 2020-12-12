---
description: 詳細については、「リソースコンパイラエラー RW2001」を参照してください。
title: リソース コンパイラ エラー RW2001
ms.date: 11/04/2016
f1_keywords:
- RW2001
helpviewer_keywords:
- RW2001
ms.assetid: 963bdc7d-6ebe-4378-8bbc-47dfcf5d330c
ms.openlocfilehash: e550854af4d504e484b722050f0274887956f2c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337258"
---
# <a name="resource-compiler-error-rw2001"></a>リソース コンパイラ エラー RW2001

前処理される RC ファイルのディレクティブが無効です

RC ファイルには、 **#pragma** ディレクティブが含まれています。

**#Ifndef** プリプロセッサディレクティブは、インクルードファイルを処理するときにリソースコンパイラが定義する **RC_INVOKED** 定数と共に使用します。 **#Pragma** ディレクティブを、 **RC_INVOKED** 定数が定義されているときに処理されないコードブロック内に配置します。 ブロック内のコードは、リソースコンパイラによってではなく、C/c + + コンパイラによってのみ処理されます。 次のサンプルコードは、この手法を示しています。

```
#ifndef RC_INVOKED
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler
#endif
```

**#Pragma** プリプロセッサディレクティブは、に意味がありません。RC ファイル。 **#Include** プリプロセッサディレクティブは、で頻繁に使用されます。RC ファイルにヘッダーファイルが含まれています (プロジェクトベースのカスタムヘッダーファイル、または Microsoft によって提供される標準ヘッダーファイルを製品のいずれかと共に使用)。 これらのインクルードファイルには、 **#pragma** ディレクティブが含まれています。 ヘッダーファイルには、他の1つ以上のヘッダーファイルを含めることができるため、問題のある **#pragma** ディレクティブを含むファイルはすぐにはわからない可能性があります。

**#Ifndef RC_INVOKED** 技法では、プロジェクトベースのヘッダーファイルにヘッダーファイルを含めるように制御できます。
