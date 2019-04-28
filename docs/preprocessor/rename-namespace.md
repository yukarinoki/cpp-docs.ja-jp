---
title: rename_namespace
ms.date: 10/18/2018
f1_keywords:
- rename_namespace
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
ms.openlocfilehash: 7b3917a7114ca44d092f10a7831bb35bc64e9387
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179764"
---
# <a name="renamenamespace"></a>rename_namespace

**C++ 固有の仕様**

タイプ ライブラリの内容を含む名前空間の名前を変更します。

## <a name="syntax"></a>構文

```
rename_namespace("NewName")
```

### <a name="parameters"></a>パラメーター

*NewName*<br/>
名前空間の新しい名前。

## <a name="remarks"></a>Remarks

1 つの引数を受け取る*NewName*、新しい名前空間の名前を指定します。

名前空間を削除するには、使用、 [no_namespace](../preprocessor/no-namespace.md)属性の代わりにします。

**END C 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)