---
title: コンパイラ COM のグローバル関数
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 74449d26-50a2-47c7-b175-7cf2cf83533e
ms.openlocfilehash: c0a9c742ad9dcbb05ed2d78c954d5a597e3b57cb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189781"
---
# <a name="compiler-com-global-functions"></a>コンパイラ COM のグローバル関数

**Microsoft 固有の仕様**

使用できるルーチンは次のとおりです。

|Function|説明|
|--------------|-----------------|
|[_com_raise_error](../cpp/com-raise-error.md)|エラーへの応答として[_com_error](../cpp/com-error-class.md)をスローします。|
|[_set_com_error_handler](../cpp/set-com-error-handler.md)|COM のエラー処理に使用する既定の関数を置き換えます。|
|[ConvertBSTRToString](../cpp/convertbstrtostring.md)|`BSTR` 値を `char *` に変換します。|
|[ConvertStringToBSTR](../cpp/convertstringtobstr.md)|`char *` 値を `BSTR` に変換します。|

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)<br/>
[コンパイラ COM サポート](../cpp/compiler-com-support.md)
