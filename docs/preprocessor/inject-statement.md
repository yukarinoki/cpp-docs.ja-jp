---
title: inject_statement
ms.date: 10/18/2018
f1_keywords:
- inject_statement
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
ms.openlocfilehash: 237ca796028aad7aff55442eb2806fe400330a29
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383725"
---
# <a name="injectstatement"></a>inject_statement

**C++ 固有の仕様**

タイプ ライブラリ ヘッダーに引数をソース テキストとして挿入します。

## <a name="syntax"></a>構文

```
inject_statement("source_text")
```

### <a name="parameters"></a>パラメーター

*source_text*<br/>
タイプ ライブラリ ヘッダー ファイルに挿入するソース テキスト。

## <a name="remarks"></a>Remarks

テキストは、ヘッダー ファイルのタイプ ライブラリの内容をラップする名前空間宣言の先頭に配置されます。

**END C 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)