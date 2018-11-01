---
title: longjmp
ms.date: 08/14/2018
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
helpviewer_keywords:
- restoring stack environment and execution locale
- longjmp function
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
ms.openlocfilehash: 56f050b5f59767fff04586d7d985cafe6d529b83
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626708"
---
# <a name="longjmp"></a>longjmp

設定されたスタック環境と実行ロケールを復元する`setjmp`呼び出します。

## <a name="syntax"></a>構文

```C
void longjmp(
   jmp_buf env,
   int value
);
```

### <a name="parameters"></a>パラメーター

*env*<br/>
環境が格納されている変数。

*値*<br/>
`setjmp` 呼び出しに返される値。

## <a name="remarks"></a>Remarks

**Longjmp**関数は、以前に保存したスタック環境と実行ロケールを復元*env*によって`setjmp`します。 `setjmp` **longjmp** 、非ローカルを実行する方法を提供**goto**; 通常の呼び出しを使用せず、以前に呼び出されたルーチンのエラー処理または回復コードに実行の制御を渡すに通常使用されます規約や復帰規約。

呼び出し`setjmp`、現在のスタック環境を保存すると、 *env*します。 後続の呼び出し**longjmp**保存済みの環境を復元し、対応する直後の位置にコントロールを返します`setjmp`呼び出します。 実行は、*value* が `setjmp` 呼び出しによって返されたかのように再開されます。 コントロールを受け取るルーチンにアクセスできるすべての変数 (レジスタ変数) を除くの値にいたときに値を含む**longjmp**が呼び出されました。 レジスタ変数の値は予測できません。 `setjmp` によって返される値は、0 以外である必要があります。 *value* が 0 として渡される場合、実際の戻り値では 1 が代入されます。

**Microsoft 固有の仕様**

Windows、Microsoft C コードで**longjmp**例外処理コードと同じスタック アンワインド セマンティクスを使用します。 C++ の例外が発生することと同じ場所で使用しても安全になります。 ただし、この使用法は、ポータブルでないし、いくつかの重要な注意事項が付属しています。

のみを呼び出す**longjmp**と呼ばれる関数の前に`setjmp`を返します。 それ以外の場合、結果は予測可能な。

使用する場合は、次の制限を観察**longjmp**:

- レジスタ変数の値は変わらないと見なさないでください。 呼び出すルーチンのレジスタ変数の値`setjmp`後に適切な値に復元されない場合があります**longjmp**を実行します。

- 使用しない**longjmp**割り込みが浮動小数点例外によって発生した場合を除き、割り込み処理ルーチンから制御を転送します。 この場合、プログラムが介して割り込みハンドラーから返す可能性があります**longjmp**が最初に再初期化浮動小数点演算パッケージを呼び出して[_fpreset](fpreset.md)します。

- 使用しない**longjmp** Windows コードで直接または間接的を呼び出されるコールバック ルーチンから制御を転送します。

- 使用して、コードがコンパイルされている場合 **/EHs**または **/EHsc**関数が含まれていますが、 **longjmp**呼び出しは**noexcept**しローカル オブジェクトその関数は、スタック アンワインド中に消滅されない可能性があります。

**Microsoft 固有の仕様はここまで**

> [!NOTE]
> 移植可能な C++ コードではできないと仮定`setjmp`と`longjmp`C++ オブジェクト セマンティクスをサポートします。 具体的を`setjmp` / `longjmp`ペアは、置き換える場合、動作は未定義の呼び出し、`setjmp`と`longjmp`によって**キャッチ**と**スロー**を呼び出します自動オブジェクトの重要なデストラクターには。 C++ プログラムは、C++ 例外処理機構を使用することをお勧めします。

詳細については、「[setjmp/longjmp の使用](../../cpp/using-setjmp-longjmp.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**longjmp**|\<setjmp.h >|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[_fpreset](fpreset.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[setjmp](setjmp.md)
