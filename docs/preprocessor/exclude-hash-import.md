---
title: 除外 (#import) |Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- exclude
dev_langs:
- C++
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c345d9268f63a714eeae4beff78a7ac39ce545a1
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49807901"
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