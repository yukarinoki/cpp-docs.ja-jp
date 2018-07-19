---
title: setjmp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- setjmp
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
apitype: DLLExport
f1_keywords:
- setjmp
dev_langs:
- C++
helpviewer_keywords:
- programs [C++], saving states
- current state
- setjmp function
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2cc4673485577f5a12024d31e94063c82a8c7b8c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407253"
---
# <a name="setjmp"></a>setjmp

プログラムの現在の状態を保存します。

## <a name="syntax"></a>構文

```C
int setjmp(
   jmp_buf env
);
```

### <a name="parameters"></a>パラメーター

*env*<br/>
環境が格納されている変数。

## <a name="return-value"></a>戻り値

スタックの環境を保存した後に 0 を返します。 場合**setjmp**の結果として返されます、 **longjmp**を呼び出すと、それを返します、**値**の引数**longjmp**、または、**値**の引数**longjmp** 0 の場合は、 **setjmp** 1 を返します。 エラーの戻り値はありません。

## <a name="remarks"></a>コメント

**Setjmp**関数は、後で復元できますを使用して、スタックの環境を保存**longjmp**です。 同時に、使用時に**setjmp**と**longjmp**非ローカルの実行方法を提供**goto**です。 これらは一般的に、通常の呼び出し規約や復帰規約を使用せず、前に呼び出されたルーチンのエラー処理または回復コードに実行の制御を渡すために使用されます。

呼び出し**setjmp**で現在のスタック環境を保存*env*です。 後続の呼び出しに**longjmp**保存されている環境を復元し、直後に、対応した後ポイントにコントロールを返します**setjmp**呼び出します。 すべての変数 (レジスタ変数) を除く制御を受け取るルーチンにアクセスできるときに保持していた値が含まれて**longjmp**が呼び出されました。

使用することはできません**setjmp**にネイティブ コードからマネージ コードに移動するようにします。

**注** **setjmp**と**longjmp** C++ オブジェクトのセマンティクスをサポートしていません。 C++ プログラムでは、C++ 例外処理機構を使用します。

詳細については、「[setjmp/longjmp の使用](../../cpp/using-setjmp-longjmp.md)」を参照してください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**setjmp**|\<setjmp.h >|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[_fpreset](fpreset.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[longjmp](longjmp.md)<br/>
[_setjmp3](../../c-runtime-library/setjmp3.md)<br/>
