---
title: _lsearch_s
ms.date: 11/04/2016
apiname:
- _lsearch_s
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _lsearch_s
- lsearch_s
helpviewer_keywords:
- linear searching
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- searching, linear
- _lsearch_s function
- lsearch_s function
ms.assetid: d2db0635-be7a-4799-8660-255f14450882
ms.openlocfilehash: f57a96622419e3f72fc2df5b260cbbbdd59666ae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156957"
---
# <a name="lsearchs"></a>_lsearch_s

値の線形探索を実行します。 「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_lsearch](lsearch.md) です。

## <a name="syntax"></a>構文

```C
void *_lsearch_s(
   const void *key,
   void *base,
   unsigned int *num,
   size_t size,
   int (__cdecl *compare)(void *, const void *, const void *),
   void * context
);
```

### <a name="parameters"></a>パラメーター

*key*<br/>
検索するオブジェクト。

*base*<br/>
検索する配列のベースへのポインター。

*number*<br/>
要素の数。

*size*<br/>
バイト単位での配列の各要素のサイズ。

*compare*<br/>
比較ルーチンへのポインター。 2 番目のパラメーターは、検索用のキーへのポインターです。 3 番目のパラメーターは、そのキーと比較する配列要素へのポインターです。

*context*<br/>
比較関数内でアクセスされることのあるオブジェクトへのポインター。

## <a name="return-value"></a>戻り値

場合*キー*が見つかると、 **_lsearch_s**配列の要素へのポインターを返します*基本*と一致する*キー*します。 場合*キー*が見つからない **_lsearch_s**配列の末尾に新しく追加された項目へのポインターを返します。

この関数に無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 続行し、実行が許可された場合**errno**に設定されている**EINVAL** 、関数を返します**NULL**します。 詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

### <a name="error-conditions"></a>エラー条件

|*key*|*base*|*compare*|*number*|*size*|**errno**|
|-----------|------------|---------------|-----------|------------|-------------|
|**NULL**|任意|任意|任意|任意|**EINVAL**|
|任意|**NULL**|任意|!= 0|任意|**EINVAL**|
|任意|任意|任意|任意|ゼロ|**EINVAL**|
|任意|任意|**NULL**|1 つ|任意|**EINVAL**|

## <a name="remarks"></a>Remarks

**_Lsearch_s**関数は、値に関して線形探索を実行します。*キー*の配列の*数*の各要素は、*幅*バイト。 異なり**bsearch_s**、 **_lsearch_s**配列を並べ替えるには必要ありません。 場合*キー*が見つからない、 **_lsearch_s**インクリメント、配列の末尾に追加*数*します。

*比較*関数は、2 つの配列要素を比較し、それらの関係を示す値を返します、ユーザー指定のルーチンへのポインター。 *比較*関数も、最初の引数としてコンテキストへのポインターを受け取ります。 **_lsearch_s**呼び出し*比較*呼び出しごとに 2 つの配列要素へのポインターを渡す、検索中に 1 つ以上の時間。 *比較*要素を比較し、いずれかを返す必要があります (つまり、要素が異なる) 0 以外の値または 0 (つまり、要素が同じ場合)。

*コンテキスト*ポインターは検索対象のデータ構造体がオブジェクトの一部である場合に便利にできる、*比較*関数は、オブジェクトのメンバーにアクセスする必要があります。 コード例については、*比較*関数はそのオブジェクトの適切なオブジェクトの種類とアクセスのメンバーに void ポインターをキャストすることができます。 追加、*コンテキスト*ポインターにより **_lsearch_s**追加のコンテキストに関連付けられたデータを使用できるようにする静的変数を使用して、再入バグを回避するために使用できるためのより安全な*比較*関数。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_lsearch_s**|\<search.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lfind_s](lfind-s.md)<br/>
[_lsearch](lsearch.md)<br/>
