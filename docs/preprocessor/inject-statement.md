---
title: inject_statement |Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- inject_statement
dev_langs:
- C++
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27b35c10e9e1953dc45dee1caf61d2e58c38d02d
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808644"
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