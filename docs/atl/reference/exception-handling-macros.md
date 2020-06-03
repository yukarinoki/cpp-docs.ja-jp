---
title: 例外処理マクロ
ms.date: 11/04/2016
f1_keywords:
- atldef/ATL::_ATLCATCH
- atldef/ATL::_ATLCATCHALL
- atldef/ATL::_ATLTRY
helpviewer_keywords:
- exception handling, macros
- C++ exception handling, macros
ms.assetid: a8385d34-3fb0-4006-a42a-de045cacf0f4
ms.openlocfilehash: 2beffbbed0efee799005190bd7fd071a2087e4d9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330087"
---
# <a name="exception-handling-macros"></a>例外処理マクロ

これらのマクロは、例外処理をサポートします。

|||
|-|-|
|[_ATLCATCH](#_atlcatch)|関連付けられた`_ATLTRY`で発生したエラーを処理するステートメント。|
|[_ATLCATCHALL](#_atlcatchall)|関連付けられた`_ATLTRY`で発生したエラーを処理するステートメント。|
|[_ATLTRY](#_atltry)|エラーが発生する可能性のある保護されたコード セクションをマークします。|

## <a name="requirements"></a>要件:

**ヘッダー:** atldef.h

## <a name="_atlcatch"></a><a name="_atlcatch"></a>_ATLCATCH

関連付けられた`_ATLTRY`で発生したエラーを処理するステートメント。

```
_ATLCATCH(e)
```

### <a name="parameters"></a>パラメーター

*E*<br/>
キャッチする例外。

### <a name="remarks"></a>解説

と組み合`_ATLTRY`わせて使用します。 C++ 例外の特定の型を処理するための C++[キャッチ (CAtlException e)](../../cpp/try-throw-and-catch-statements-cpp.md)に解決します。

## <a name="_atlcatchall"></a><a name="_atlcatchall"></a>_ATLCATCHALL

関連付けられた`_ATLTRY`で発生したエラーを処理するステートメント。

```
_ATLCATCHALL
```

### <a name="remarks"></a>解説

と組み合`_ATLTRY`わせて使用します。 すべての種類の C++ 例外を処理するために C++ [catch(..)](../../cpp/try-throw-and-catch-statements-cpp.md)に解決します。

## <a name="_atltry"></a><a name="_atltry"></a>_ATLTRY

エラーが発生する可能性のある保護されたコード セクションをマークします。

```
_ATLTRY
```

### <a name="remarks"></a>解説

[_ATLCATCH](#_atlcatch)または[_ATLCATCHALL](#_atlcatchall)と組み合わせて使用します。 C++ シンボル[try](../../cpp/try-throw-and-catch-statements-cpp.md)に解決します。

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)
