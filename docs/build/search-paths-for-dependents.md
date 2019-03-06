---
title: 依存ファイルの検索パス
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
ms.openlocfilehash: 9f2251a5fff9d708a783797d04606572e5ebce62
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57426460"
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
