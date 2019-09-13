---
title: _callnewh
ms.date: 11/04/2016
apiname:
- _callnewh
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _callnewh
helpviewer_keywords:
- _callnewh
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
ms.openlocfilehash: 98526f6c8c40b71104345563db71ef098b6cfb8d
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70739821"
---
# <a name="_callnewh"></a>_callnewh

現在インストールされている*新しいハンドラー*を呼び出します。

## <a name="syntax"></a>構文

```cpp
int _callnewh(
   size_t size
   )
```

### <a name="parameters"></a>パラメーター

*size*<br/>
[new 演算子](../../cpp/new-operator-cpp.md)が割り当てようとしたメモリの量。

## <a name="return-value"></a>戻り値

|値|説明|
|-----------|-----------------|
|0|不具合新しいハンドラーがインストールされていないか、新しいハンドラーがアクティブになっていません。|
|1|ブランド新しいハンドラーがインストールされ、アクティブになります。 メモリ割り当てを再試行できます。|

## <a name="exceptions"></a>例外

*新しいハンドラー*が見つからない場合、[bad_alloc](../../standard-library/bad-alloc-class.md) をスローします。

## <a name="remarks"></a>Remarks

*新しいハンドラー*は、[new 演算子](../../cpp/new-operator-cpp.md)がメモリの割り当てに失敗した場合に呼び出されます。 新しいハンドラーは、後続の割り当てが成功するようにメモリを解放するなど、適切な処理を開始する場合があります。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|_callnewh|internal.h|

## <a name="see-also"></a>関連項目

[_set_new_handler](set-new-handler.md)<br/>
[_set_new_mode](set-new-mode.md)<br/>
