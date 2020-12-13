---
description: 詳細については、「コンパイラ COM グローバル関数」を参照してください。
title: コンパイラ COM のグローバル関数
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 74449d26-50a2-47c7-b175-7cf2cf83533e
ms.openlocfilehash: d678372bdc5703aa05fdf093b84075b7286c4b9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335549"
---
# <a name="compiler-com-global-functions"></a>コンパイラ COM のグローバル関数

**Microsoft 固有の仕様**

使用できるルーチンは次のとおりです。

|機能|説明|
|--------------|-----------------|
|[_com_raise_error](../cpp/com-raise-error.md)|エラーへの応答として [_com_error](../cpp/com-error-class.md) をスローします。|
|[_set_com_error_handler](../cpp/set-com-error-handler.md)|COM のエラー処理に使用する既定の関数を置き換えます。|
|[ConvertBSTRToString](../cpp/convertbstrtostring.md)|`BSTR` 値を `char *` に変換します。|
|[ConvertStringToBSTR](../cpp/convertstringtobstr.md)|`char *` 値を `BSTR` に変換します。|

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラ COM サポートクラス](../cpp/compiler-com-support-classes.md)<br/>
[コンパイラの COM サポート](../cpp/compiler-com-support.md)
