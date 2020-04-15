---
title: _lsearch_s
ms.date: 4/2/2020
api_name:
- _lsearch_s
- _o__lsearch_s
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 720b83dd48b42d77f35bce12f16e8ac79eb3b4d3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341650"
---
# <a name="_lsearch_s"></a>_lsearch_s

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

*数*<br/>
要素の数。

*サイズ*<br/>
バイト単位での配列の各要素のサイズ。

*比較*<br/>
比較ルーチンへのポインター。 2 番目のパラメーターは、検索用のキーへのポインターです。 3 番目のパラメーターは、そのキーと比較する配列要素へのポインターです。

*context*<br/>
比較関数内でアクセスされることのあるオブジェクトへのポインター。

## <a name="return-value"></a>戻り値

*key*が見つかった場合 **、_lsearch_s**は *、key*に一致する*配列*の要素へのポインターを返します。 *key*が見つからない場合 **、_lsearch_s**は配列の末尾に新しく追加された項目へのポインターを返します。

この関数に無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合 **、errno**は**EINVAL**に設定され、関数は**NULL**を返します。 詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

### <a name="error-conditions"></a>エラー条件

|*key*|*base*|*比較*|*数*|*サイズ*|**errno**|
|-----------|------------|---------------|-----------|------------|-------------|
|**NULL**|any|any|any|any|**Einval**|
|any|**NULL**|any|!= 0|any|**Einval**|
|any|any|any|any|ゼロ|**Einval**|
|any|any|**NULL**|1 つ|any|**Einval**|

## <a name="remarks"></a>解説

**_lsearch_s**関数は、*数値要素の*配列 (*幅*のバイトの各配列) の値*キー*の線形検索を実行します。 **bsearch_s**とは異なり **、_lsearch_s**配列を並べ替える必要はありません。 *key*が見つからない場合 **、_lsearch_s**は配列の末尾に追加し、*番号*を増やします。

*compare*関数は、2 つの配列要素を比較し、それらの関係を指定する値を返すユーザー提供ルーチンへのポインターです。 *比較*関数は、最初の引数としてコンテキストへのポインターも受け取ります。 **_lsearch_s**呼び出しは、検索中に 1 回以上*比較*され、各呼び出しで 2 つの配列要素へのポインターを渡します。 *compare*は、要素を比較してから、0 以外 (要素が異なることを意味します) または 0 (要素が同一であることを意味します) を返す必要があります。

*コンテキスト*ポインターは、検索されたデータ構造体がオブジェクトの一部であり、*比較*関数がオブジェクトのメンバーにアクセスする必要がある場合に役立ちます。 たとえば、*比較*関数のコードは、void ポインターを適切なオブジェクト型にキャストし、そのオブジェクトのメンバーにアクセスできます。 *コンテキスト*ポインターを追加すると、静的変数を使用して*比較関数で*データを使用できるようにするために、追加のコンテキストを使用して再入可能なバグを回避できるため **、_lsearch_s**の安全性が高まります。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_lsearch_s**|\<search.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[検索と並べ替え](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lfind_s](lfind-s.md)<br/>
[_lsearch](lsearch.md)<br/>
