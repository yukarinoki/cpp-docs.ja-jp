---
description: 詳細については、「リソースコンパイラエラー RC2101」を参照してください。
title: リソース コンパイラ エラー RC2101
ms.date: 11/04/2016
f1_keywords:
- RC2101
helpviewer_keywords:
- RC2101
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
ms.openlocfilehash: bed2490f48f40c94724fa249f7722a290cf8d9b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164134"
---
# <a name="resource-compiler-error-rc2101"></a>リソース コンパイラ エラー RC2101

前処理される RC ファイルのディレクティブが無効です

リソースコンパイラファイルには、 **#pragma** ディレクティブが含まれています。

**#Ifndef** プリプロセッサディレクティブは、インクルードファイルを処理するときにリソースコンパイラが定義する RC_INVOKED 定数と共に使用します。 **#Pragma** ディレクティブを、RC_INVOKED 定数が定義されているときに処理されないコードブロック内に配置します。 ブロック内のコードは、リソースコンパイラによってではなく、C/c + + コンパイラによってのみ処理されます。 次のサンプルコードは、この手法を示しています。

```
#ifndef RC_INVOKED
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler
#endif
```

**#Pragma** プリプロセッサディレクティブは、に意味がありません。RC ファイル。 **#Include** プリプロセッサディレクティブは、で頻繁に使用されます。RC ファイルにヘッダーファイルが含まれています (プロジェクトベースのカスタムヘッダーファイル、または Microsoft によって提供される標準ヘッダーファイルを製品のいずれかと共に使用)。 これらのインクルードファイルには、 **#pragma** ディレクティブが含まれています。 ヘッダーファイルには、他の1つ以上のヘッダーファイルを含めることができるため、問題のある **#pragma** ディレクティブを含むファイルはすぐにはわからない可能性があります。

**#Ifndef** RC_INVOKED 技法では、プロジェクトベースのヘッダーファイルにヘッダーファイルを含めるように制御できます。
