---
title: リソース コンパイラ エラー RC2101
ms.date: 11/04/2016
f1_keywords:
- RC2101
helpviewer_keywords:
- RC2101
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
ms.openlocfilehash: 3fb576758e447c54e4ddfe7ddb024a1fd35a65f2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80191653"
---
# <a name="resource-compiler-error-rc2101"></a>リソース コンパイラ エラー RC2101

前処理される RC ファイルのディレクティブが無効です

リソースコンパイラファイルには、 **#pragma**ディレクティブが含まれています。

**#Ifndef**プリプロセッサディレクティブは、インクルードファイルを処理するときにリソースコンパイラが定義する RC_INVOKED 定数と共に使用します。 **#Pragma**ディレクティブを、RC_INVOKED 定数が定義されているときに処理されないコードブロック内に配置します。 ブロック内のコードは、リソースコンパイラによってC++ではなく、C/コンパイラによってのみ処理されます。 次のサンプルコードは、この手法を示しています。

```
#ifndef RC_INVOKED
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler
#endif
```

**#Pragma**プリプロセッサディレクティブは、に意味がありません。RC ファイル。 **#Include**プリプロセッサディレクティブは、で頻繁に使用されます。RC ファイルにヘッダーファイルが含まれています (プロジェクトベースのカスタムヘッダーファイル、または Microsoft によって提供される標準ヘッダーファイルを製品のいずれかと共に使用)。 これらのインクルードファイルには、 **#pragma**ディレクティブが含まれています。 ヘッダーファイルには、他の1つ以上のヘッダーファイルを含めることができるため、問題のある **#pragma**ディレクティブを含むファイルはすぐにはわからない可能性があります。

**#Ifndef** RC_INVOKED 技法では、プロジェクトベースのヘッダーファイルにヘッダーファイルを含めるように制御できます。
