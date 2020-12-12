---
description: '詳細情報: 例外処理マクロ'
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
ms.openlocfilehash: 8d5e6564dec5769fb172c66b3102677e58cbd788
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139829"
---
# <a name="exception-handling-macros"></a>例外処理マクロ

これらのマクロは、例外処理のサポートを提供します。

|名前|説明|
|-|-|
|[_ATLCATCH](#_atlcatch)|関連付けられているで発生したエラーを処理するステートメント `_ATLTRY` 。|
|[_ATLCATCHALL](#_atlcatchall)|関連付けられているで発生したエラーを処理するステートメント `_ATLTRY` 。|
|[_ATLTRY](#_atltry)|エラーが発生する可能性がある、保護されたコードセクションをマークします。|

## <a name="requirements"></a>要件:

**ヘッダー:** atldef. h

## <a name="_atlcatch"></a><a name="_atlcatch"></a> _ATLCATCH

関連付けられているで発生したエラーを処理するステートメント `_ATLTRY` 。

```
_ATLCATCH(e)
```

### <a name="parameters"></a>パラメーター

*e*<br/>
キャッチする例外。

### <a name="remarks"></a>解説

と組み合わせて使用 `_ATLTRY` します。 特定の種類の C++ 例外を処理するために、C++ [catch (CAtlException e)](../../cpp/try-throw-and-catch-statements-cpp.md) に解決されます。

## <a name="_atlcatchall"></a><a name="_atlcatchall"></a> _ATLCATCHALL

関連付けられているで発生したエラーを処理するステートメント `_ATLTRY` 。

```
_ATLCATCHALL
```

### <a name="remarks"></a>解説

と組み合わせて使用 `_ATLTRY` します。 C++ の [catch (...)](../../cpp/try-throw-and-catch-statements-cpp.md) に解決され、すべての種類の c++ 例外を処理します。

## <a name="_atltry"></a><a name="_atltry"></a> _ATLTRY

エラーが発生する可能性がある、保護されたコードセクションをマークします。

```
_ATLTRY
```

### <a name="remarks"></a>解説

[_ATLCATCH](#_atlcatch)または[_ATLCATCHALL](#_atlcatchall)と組み合わせて使用されます。 C++ シンボル [try](../../cpp/try-throw-and-catch-statements-cpp.md)に解決されます。

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)
