---
title: _findnext、_findnext32、_findnext32i64、_findnext64、_findnext64i32、_findnexti64、_wfindnext、_wfindnext32、_wfindnext32i64、_wfindnext64、_wfindnext64i32、_wfindnexti64
ms.date: 11/04/2016
apiname:
- _wfindnext
- _findnext
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- findnext
- _wfindnext32i64
- _tfindnext64i32
- findnext32
- findnext32i64
- wfindnext64i32
- _wfindnext
- tfindnext64
- findnexti64
- _findnexti64
- _tfindnexti64
- _findnext64i32
- tfindnexti64
- tfindnext32
- _wfindnext64i32
- findnext64i32
- _findnext
- _tfindnext32i64
- _wfindnext64
- wfindnext
- wfindnext32
- tfindnext32i64
- _findnext64
- _tfindnext64
- _wfindnext32
- findnext64
- _findnext32i64
- tfindnext
- wfindnexti64
- tfindnext64i32
- _tfindnext32
- wfindnext32i64
- wfindnext64
- _wfindnexti64
- _tfindnext
- _findnext32
helpviewer_keywords:
- _wfindnexti64 function
- _tfindnext32 function
- wfindnexti64 function
- _wfindnext32i64 function
- findnext32i64 function
- tfindnext64i32 function
- _tfindnext64i32 function
- _findnext function
- findnext64i32 function
- _tfindnext function
- findnext32 function
- tfindnext32 function
- _findnext32 function
- _tfindnext32i64 function
- _wfindnext function
- tfindnext function
- _findnext64 function
- findnext64 function
- _findnext64i32 function
- wfindnext32i64 function
- findnext function
- wfindnext32 function
- _wfindnext64i32 function
- findnexti64 function
- _wfindnext64 function
- _findnext32i64 function
- _findnexti64 function
- _tfindnext64 function
- wfindnext64i32 function
- tfindnexti64 function
- wfindnext64 function
- wfindnext function
- tfindnext64 function
- _wfindnext32 function
- tfindnext32i64 function
- _tfindnexti64 function
ms.assetid: 75d97188-5add-4698-a46c-4c492378f0f8
ms.openlocfilehash: c7df8649625488a83239a19e4afcecea129f9072
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51329450"
---
# <a name="findnext-findnext32-findnext32i64-findnext64-findnext64i32-findnexti64-wfindnext-wfindnext32-wfindnext32i64-wfindnext64-wfindnext64i32-wfindnexti64"></a>_findnext、_findnext32、_findnext32i64、_findnext64、_findnext64i32、_findnexti64、_wfindnext、_wfindnext32、_wfindnext32i64、_wfindnext64、_wfindnext64i32、_wfindnexti64

すべてに一致する場合は、次の名前を検索、 *filespec*以前の呼び出しで引数[_findfirst](findfirst-functions.md)とその変更、 *fileinfo*内容を適切に構造体します。

## <a name="syntax"></a>構文

```C
int _findnext(
   intptr_t handle,
   struct _finddata_t *fileinfo
);
int _findnext32(
   intptr_t handle,
   struct _finddata32_t *fileinfo
);
int _findnext64(
   intptr_t handle,
   struct __finddata64_t *fileinfo
);
int _findnexti64(
   intptr_t handle,
   struct __finddatai64_t *fileinfo
);
int _findnext32i64(
   intptr_t handle,
   struct _finddata32i64_t *fileinfo
);
int _findnext64i32(
   intptr_t handle,
   struct _finddata64i32_t *fileinfo
);
int _wfindnext(
   intptr_t handle,
   struct _wfinddata_t *fileinfo
);
int _wfindnext32(
   intptr_t handle,
   struct _wfinddata32_t *fileinfo
);
int _wfindnext64(
   intptr_t handle,
   struct _wfinddata64_t *fileinfo
);
int _wfindnexti64(
   intptr_t handle,
   struct _wfinddatai64_t *fileinfo
);
int _wfindnext32i64(
   intptr_t handle,
   struct _wfinddatai64_t *fileinfo
);
int _wfindnext64i32(
   intptr_t handle,
   struct _wfinddata64i32_t *fileinfo
);
```

### <a name="parameters"></a>パラメーター

*handle*<br/>
以前の呼び出しによって返された検索ハンドル **_findfirst**します。

*fileinfo*<br/>
ファイル情報バッファー。

## <a name="return-value"></a>戻り値

正常に終了した場合は、0 を返します。 それ以外の場合、-1 を返し、設定**errno**エラーの性質を示す値にします。 次の表に、発生する可能性のあるエラー コードを示します。

|errno の値|条件|
|-|-|
| **EINVAL** | 無効なパラメーター: *fileinfo*が**NULL**します。 または、オペレーティング システムが予期しないエラーを返しました。 |
| **ENOENT** | これ以上一致するファイルが見つかりません。 |
| **ENOMEM** | 十分なメモリまたはファイル名の長さが超過**MAX_PATH**します。 |

無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、これらの関数は無効なパラメーター ハンドラーを呼び出します。

## <a name="remarks"></a>Remarks

呼び出す必要があります[_findclose](findclose.md)を使用していずれかが完了した後、 **_findfirst**または **_findnext**関数 (または任意のバリアント)。 呼び出すと、アプリケーション内でこれらの関数が使用しているリソースが解放されます。

これらの関数のバリエーション、 **w**プレフィックスはワイド文字バージョンは、それ以外の場合、対応する 1 バイト関数と同じです。

これらの関数のバリエーションは、32 ビットや 64 ビットの時刻型と、32 ビットや 64 ビットのファイル サイズをサポートします。 最初の数字のサフィックス (**32**または**64**) 時間のサイズを表します型の使用は、2 番目のサフィックスは**i32**または**i64**、。ファイル サイズが 32 ビットまたは 64 ビット整数として表されるかどうかを示すです。 32 ビットと 64 ビットの時刻型とファイル サイズをサポートするバージョンについては、次の表を参照してください。 64 ビットの時刻型を使用するバリエーションでは、3000 年 12 月 31 日 23:59:59 (UTC) までのファイルの作成日を表現できます。32 ビットの時刻型を使用するバリエーションでは、2038 年 1 月 18 日 23:59:59 (UTC) までの日付のみを表現できます。 これらの関数の日付範囲の下限は、いずれも 1970 年 1 月 1 日の午前 0 時です。

時間のサイズを明示的に指定するバージョンを使用する特定の理由がない限り **_findnext**または **_wfindnext** 3 GB を超えるファイル サイズをサポートする必要がある場合、または、 **_findnexti64**または **_wfindnexti64**します。 これらの関数はすべて 64 ビットの時刻型です。 以前のバージョンでは、これらの関数は 32 ビットの時刻型を使用していました。 アプリケーションの互換性に影響する変更の場合は、定義 **_USE_32BIT_TIME_T**を以前の動作を取得します。 場合 **_USE_32BIT_TIME_T**が定義されている **_findnext**、 **_finnexti64**とそれに対応する Unicode バージョンは 32 ビットの時刻を使用します。

### <a name="time-type-and-file-length-type-variations-of-findnext"></a>_findnext の時刻型とファイル長型のバリエーション

|関数|**_USE_32BIT_TIME_T**定義されているか。|時刻型|ファイル長型|
|---------------|----------------------------------|---------------|----------------------|
|**_findnext**、 **_wfindnext**|未定義|64 ビット|32 ビット|
|**_findnext**、 **_wfindnext**|定義済み|32 ビット|32 ビット|
|**_findnext32**、 **_wfindnext32**|マクロ定義の影響を受けない|32 ビット|32 ビット|
|**_findnext64**、 **_wfindnext64**|マクロ定義の影響を受けない|64 ビット|64 ビット|
|**_findnexti64**、 **_wfindnexti64**|未定義|64 ビット|64 ビット|
|**_findnexti64**、 **_wfindnexti64**|定義済み|32 ビット|64 ビット|
|**_findnext32i64**、 **_wfindnext32i64**|マクロ定義の影響を受けない|32 ビット|64 ビット|
|**_findnext64i32**、 **_wfindnext64i32**|マクロ定義の影響を受けない|64 ビット|32 ビット|

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfindnext**|**_findnext**|**_findnext**|**_wfindnext**|
|**_tfindnext32**|**_findnext32**|**_findnext32**|**_wfindnext32**|
|**_tfindnext64**|**_findnext64**|**_findnext64**|**_wfindnext64**|
|**_tfindnexti64**|**_findnexti64**|**_findnexti64**|**_wfindnexti64**|
|**_tfindnext32i64**|**_findnext32i64**|**_findnext32i64**|**_wfindnext32i64**|
|**_tfindnext64i32**|**_findnext64i32**|**_findnext64i32**|**_wfindnext64i32**|

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**_findnext**|\<io.h>|
|**_findnext32**|\<io.h>|
|**_findnext64**|\<io.h>|
|**_findnexti64**|\<io.h>|
|**_findnext32i64**|\<io.h>|
|**_findnext64i32**|\<io.h>|
|**_wfindnext**|\<io.h> または \<wchar.h>|
|**_wfindnext32**|\<io.h> または \<wchar.h>|
|**_wfindnext64**|\<io.h> または \<wchar.h>|
|**_wfindnexti64**|\<io.h> または \<wchar.h>|
|**_wfindnext32i64**|\<io.h> または \<wchar.h>|
|**_wfindnext64i32**|\<io.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[システム コール](../../c-runtime-library/system-calls.md)<br/>
[ファイル名検索関数](../../c-runtime-library/filename-search-functions.md)<br/>
