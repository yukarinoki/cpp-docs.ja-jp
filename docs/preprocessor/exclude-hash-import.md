---
title: exclude (#import)
ms.date: 10/18/2018
f1_keywords:
- exclude
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
ms.openlocfilehash: d6a320089d5954b2cf1d0d96ae1f37656f2ddd58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389321"
---
# <a name="exclude-import"></a>除外 (\#インポート)

**C++ 固有の仕様**

生成されるタイプ ライブラリのヘッダー ファイルから項目を除外します。

## <a name="syntax"></a>構文

```
exclude("Name1"[, "Name2",...])
```

### <a name="parameters"></a>パラメーター

*Name1*<br/>
除外する最初の項目。

*Name2*<br/>
除外する 2 番目の項目 (必要な場合)。

## <a name="remarks"></a>Remarks

タイプ ライブラリは、システム ヘッダーまたはその他のタイプ ライブラリで定義された項目の定義を含むことがあります。 この属性は、任意の数の引数を受け取ることができます。各引数は、除外するトップ レベルのタイプ ライブラリ項目です。

**END C 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)