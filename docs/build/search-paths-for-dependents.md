---
title: 依存ファイルの検索パス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d1fd407f99abb98fb949b6d5bcc45b10c6ff9121
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706305"
---
# <a name="search-paths-for-dependents"></a>依存ファイルの検索パス

各依存では、次のように、オプションの検索パスがあります。

## <a name="syntax"></a>構文

```
{directory[;directory...]}dependent
```

## <a name="remarks"></a>Remarks

(Nmake の) は、最初に、現在のディレクトリとし、指定された順序でディレクトリの依存を検索します。 マクロは、検索パスの一部またはすべてを指定できます。 ディレクトリ名を囲む中かっこ ({});複数のディレクトリをセミコロン (;) で区切ります。 スペースまたはタブは許可されません。

## <a name="see-also"></a>関連項目

[依存](../build/dependents.md)