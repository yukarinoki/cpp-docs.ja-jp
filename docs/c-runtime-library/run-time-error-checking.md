---
description: 詳細については、「Run-Time エラーチェック」を参照してください。
title: ランタイム エラー チェック
ms.date: 11/04/2016
helpviewer_keywords:
- run-time error checking
- run-time errors, checking
ms.assetid: c965dd01-57ad-4a3c-b1d6-5aa04f920501
ms.openlocfilehash: aff00bc66cd118b891e902328eb6ae85bd6fc14c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273606"
---
# <a name="run-time-error-checking"></a>ランタイム エラー チェック

C のランタイム ライブラリには、ランタイム エラー チェック (RTC) をサポートする関数が含まれています。 ランタイム エラー チェックにより、特定の種類のランタイム エラーが報告されるようにプログラムを作成することができます。 エラーの報告方法と、報告するエラーの種類を指定できます。 詳細については、「[How to: Use Native Run-Time Checks (方法: ネイティブ ランタイム チェックを使用する)](/visualstudio/debugger/how-to-use-native-run-time-checks)」をご覧ください。

プログラムによるランタイム エラー チェックの方法をカスタマイズするには、次の関数を使用します。

## <a name="run-time-error-checking-functions"></a>ランタイム エラー チェックの関数

|機能|使用|
|--------------|---------|
|[_RTC_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md)|ランタイム エラー チェックの種類に関する簡単な説明を返します。|
|[_RTC_NumErrors](../c-runtime-library/reference/rtc-numerrors.md)|ランタイム エラー チェックで検出できるエラーの合計数を返します。|
|[_RTC_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md)|ランタイム エラー チェックを報告するためのハンドラーとして関数を指定します。|
|[_RTC_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md)|ランタイム エラー チェックで検出されたエラーを特定の種類に関連付けます。|

## <a name="see-also"></a>関連項目

[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)<br/>
[/RTC (ランタイムエラーチェック)](../build/reference/rtc-run-time-error-checks.md)<br/>
[runtime_checks](../preprocessor/runtime-checks.md)<br/>
[デバッグルーチン](../c-runtime-library/debug-routines.md)<br/>
