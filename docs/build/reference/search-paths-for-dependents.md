---
title: 依存ファイルの検索パス
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
ms.openlocfilehash: bc2c430c43f408065234c9df50977003eafd3cb1
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826701"
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

[依存](dependents.md)
