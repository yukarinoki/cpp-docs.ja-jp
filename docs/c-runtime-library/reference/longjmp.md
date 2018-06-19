---
title: longjmp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- longjmp
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
- longjmp
dev_langs:
- C++
helpviewer_keywords:
- restoring stack environment and execution locale
- longjmp function
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f6c26cae9a3fe83012387c93e31c4005d5614d97
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32401722"
---
# <a name="longjmp"></a>longjmp

スタック環境と実行ロケールを復元します。

## <a name="syntax"></a>構文

```C
void longjmp(
   jmp_buf env,
   int value
);
```

### <a name="parameters"></a>パラメーター

*env*環境が格納されている変数。

*値*に返される値**setjmp**呼び出します。

## <a name="remarks"></a>コメント

**Longjmp**関数は、以前に保存したスタック環境と実行ロケールを復元*env*によって**setjmp**です。 **setjmp**と**longjmp** 、東京を実行するための手段**goto**; せず、以前に呼び出されたルーチン内のエラー処理または回復コードに実行制御を渡す通常使用されます通常の呼び出しと戻り値の規則を使用します。

呼び出し**setjmp**で保存する現在のスタック環境*env*です。 後続の呼び出しに**longjmp**保存されている環境を復元し、対応する直後の位置に制御を返す**setjmp**呼び出します。 実行が再開されますとして*値*によって返された、 **setjmp**呼び出します。 制御を受け取るルーチンにアクセスできるすべての変数 (レジスタ変数) を除く値が保持していた場合に値を含む**longjmp**が呼び出されました。 レジスタ変数の値は予測できません。 によって返される値**setjmp** 0 以外にする必要があります。 *value* が 0 として渡される場合、実際の戻り値では 1 が代入されます。

呼び出す**longjmp**呼び出される関数の前に**setjmp**を返します。 それ以外の場合、結果は予測可能な。

使用するときは、次の制限に従う**longjmp**:

- レジスタ変数の値は変わらないと見なさないでください。 ルーチンの呼び出し元のレジスタ変数の値**setjmp**後に適切な値にならなかった場合があります**longjmp**を実行します。

- 使用しないでください**longjmp**割り込みが浮動小数点の例外が発生した場合を除き、割り込み処理ルーチンからコントロールを転送します。 ここでは、プログラムを使用して、割り込みハンドラーから戻ることが**longjmp**が、まずを再初期化する浮動小数点演算パッケージを呼び出して **_fpreset**です。

     **注**を使用する際は注意**setjmp**と**longjmp** C++ プログラムでします。 これらの関数は C++ オブジェクト セマンティクスをサポートしていないため、C++ 例外処理機構を使用する方が安全です。

詳細については、「[setjmp/longjmp の使用](../../cpp/using-setjmp-longjmp.md)」を参照してください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**longjmp**|\<setjmp.h >|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

「[_fpreset](fpreset.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[setjmp](setjmp.md)<br/>
