---
title: setjmp | Microsoft Docs
ms.custom: ''
ms.date: 08/14/2018
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
ms.openlocfilehash: 06073527aae8112d231dbd971b3daae35276efef
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2018
ms.locfileid: "42572224"
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

*env*  
環境が格納されている変数。

## <a name="return-value"></a>戻り値

スタックの環境を保存した後に 0 を返します。 場合**setjmp**の結果として返されます、`longjmp`呼び出すには、それを返します、*値*の引数`longjmp`、または、*値*の引数`longjmp`は 0 です。**setjmp** 1 を返します。 エラーの戻り値はありません。

## <a name="remarks"></a>Remarks

**Setjmp**機能が戻すことができます、その後を使用して、スタックの環境を保存します`longjmp`します。 同時に、使用すると**setjmp**と`longjmp`非ローカルを実行する方法を提供**goto**します。 これらは一般的に、通常の呼び出し規約や復帰規約を使用せず、前に呼び出されたルーチンのエラー処理または回復コードに実行の制御を渡すために使用されます。

呼び出し**setjmp**で現在のスタック環境を保存します。 *env*します。 後続の呼び出し`longjmp`保存済みの環境を復元し、対応する直後のポイントにコントロールを返します**setjmp**呼び出します。 コントロールを受け取るルーチンにアクセスできるすべての変数 (レジスタ変数を除く) には、`longjmp` が呼び出されたときに保持していた値が含まれます。

使用することはできません**setjmp**ネイティブ コードからマネージ コードにジャンプします。

**Microsoft 固有の仕様**

Windows、Microsoft C コードで**longjmp**例外処理コードと同じスタック アンワインド セマンティクスを使用します。 C++ の例外が発生することと同じ場所で使用しても安全になります。 ただし、この使用法は、ポータブルでないし、いくつかの重要な注意事項が付属しています。 詳細については、次を参照してください。 [longjmp](longjmp.md)します。

**Microsoft 固有の仕様はここまで**

> [!NOTE]  
> 移植可能な C++ コードではできないと仮定`setjmp`と`longjmp`C++ オブジェクト セマンティクスをサポートします。 具体的を`setjmp` / `longjmp`ペアは、置き換える場合、動作は未定義の呼び出し、`setjmp`と`longjmp`によって**キャッチ**と**スロー**を呼び出します自動オブジェクトの重要なデストラクターには。 C++ プログラムは、C++ 例外処理機構を使用することをお勧めします。

詳細については、「[setjmp/longjmp の使用](../../cpp/using-setjmp-longjmp.md)」を参照してください。

## <a name="requirements"></a>要件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**setjmp**|\<setjmp.h >|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[_fpreset](fpreset.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)  
[longjmp](longjmp.md)  
