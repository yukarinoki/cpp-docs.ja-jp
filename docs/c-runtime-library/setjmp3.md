---
description: '詳細については、次を参照してください: _setjmp3'
title: _setjmp3
ms.date: 1/14/2021
api_name:
- _setjmp3
api_location:
- msvcrt.dll
- msvcr90.dll
- msvcr110.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr120.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- setjmp3
- _setjmp3
helpviewer_keywords:
- _setjmp3 function
- setjmp3 function
ms.assetid: 6129c2f3-8bac-4fdb-a827-44e1eebba500
ms.openlocfilehash: 9d65f807c34d926485777d49156061196dfc0948
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "98243100"
---
# `_setjmp3`

内部 CRT 関数。 `setjmp` 関数の新しい実装。

## <a name="syntax"></a>構文

```
int _setjmp3(
   OUT jmp_buf env,
   int count,
   (optional parameters)
);
```

#### <a name="parameters"></a>パラメーター

*`env`*\
[out] 状態情報を格納するためのバッファーのアドレス。

*`count`*\
[in] `optional parameters` に格納されている情報の追加 `DWORD` の数。

*`optional parameters`*\
[in] `setjmp` の組み込みによってプッシュダウンされる追加データ。 最初の `DWORD` は、追加データをアンワインドして不揮発性レジスタの状態に戻るために使用される関数ポインターです。 2 番目の `DWORD` は、復元される試行レベルです。 これ以上のデータは、`jmp_buf` の一般的なデータ配列に保存されます。

## <a name="return-value"></a>戻り値

常に 0 を返します。

## <a name="remarks"></a>注釈

この関数は、C++ プログラムでは使用しないでください。 これは、C++ をサポートしない組み込み関数です。 `setjmp` の使用方法の詳細については、「[setjmp/longjmp の使用](../cpp/using-setjmp-longjmp.md)」をご覧ください。

## <a name="requirements"></a>要件

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](../c-runtime-library/reference/crt-alphabetical-function-reference.md)\
[`setjmp`](../c-runtime-library/reference/setjmp.md)
