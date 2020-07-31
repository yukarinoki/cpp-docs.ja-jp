---
title: setjmp
ms.date: 08/14/2018
api_name:
- setjmp
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
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- setjmp
helpviewer_keywords:
- programs [C++], saving states
- current state
- setjmp function
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
ms.openlocfilehash: beaf56a03c1bd157257d604bfd0ebefb219d0225
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226152"
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

*エンベロープ*<br/>
環境が格納されている変数。

## <a name="return-value"></a>戻り値

スタックの環境を保存した後に 0 を返します。 **Setjmp**が呼び出しの結果としてを返す場合、 `longjmp` の*値*引数を返します `longjmp` 。または、の*値*引数が0の場合 `longjmp` 、 **setjmp**は1を返します。 エラーの戻り値はありません。

## <a name="remarks"></a>解説

**Setjmp**関数は、を使用して、後で復元できるスタック環境を保存し `longjmp` ます。 **Setjmp**とを一緒に使用すると、 `longjmp` 非ローカルのを実行する方法が提供され **`goto`** ます。 これらは一般的に、通常の呼び出し規約や復帰規約を使用せず、前に呼び出されたルーチンのエラー処理または回復コードに実行の制御を渡すために使用されます。

**Setjmp**を呼び出すと、現在のスタック環境が*env*に保存されます。 の後続の呼び出しは、 `longjmp` 保存された環境を復元し、対応する**setjmp**呼び出しの直後のポイントに制御を戻します。 コントロールを受け取るルーチンにアクセスできるすべての変数 (レジスタ変数を除く) には、`longjmp` が呼び出されたときに保持していた値が含まれます。

**Setjmp**を使用して、ネイティブコードからマネージコードに移動することはできません。

**Microsoft 固有の仕様**

Windows 上の Microsoft C++ コードでは、 **longjmp**は例外処理コードと同じスタックアンワインドセマンティクスを使用します。 C++ 例外を発生させるのと同じ場所で、を安全に使用できます。 ただし、この使用方法はポータブルではなく、いくつかの重要な注意事項が付属しています。 詳細については、「 [longjmp](longjmp.md)」を参照してください。

**Microsoft 固有の仕様はここまで**

> [!NOTE]
> 移植可能な C++ コードでは、 `setjmp` c++ オブジェクトのセマンティクスを想定してサポートすることはできません `longjmp` 。 具体的には、 `setjmp` / `longjmp` とを置き換える場合、呼び出しペアの動作が未定義である `setjmp` ため、 `longjmp` **`catch`** **`throw`** 任意の自動オブジェクトに対して自明ではないデストラクターが呼び出されます。 C++ プログラムでは、C++ 例外処理機構を使用することをお勧めします。

詳細については、「[setjmp/longjmp の使用](../../cpp/using-setjmp-longjmp.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**setjmp**|\<setjmp.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[_fpreset](fpreset.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[longjmp](longjmp.md)
