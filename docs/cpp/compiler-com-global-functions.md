---
title: コンパイラ COM グローバル関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 74449d26-50a2-47c7-b175-7cf2cf83533e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb769cf1419f7a0142a5eeae348ca432f78fb92a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034142"
---
# <a name="compiler-com-global-functions"></a>コンパイラ COM のグローバル関数

**Microsoft 固有の仕様**

使用できるルーチンは次のとおりです。

|関数|説明|
|--------------|-----------------|
|[_com_raise_error](../cpp/com-raise-error.md)|スローされます、 [_com_error](../cpp/com-error-class.md)エラーに応答します。|
|[_set_com_error_handler](../cpp/set-com-error-handler.md)|COM のエラー処理に使用する既定の関数を置き換えます。|
|[ConvertBSTRToString](../cpp/convertbstrtostring.md)|変換を`BSTR`値を`char *`します。|
|[ConvertStringToBSTR](../cpp/convertstringtobstr.md)|変換を`char *`値を`BSTR`します。|

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)<br/>
[コンパイラ COM サポート](../cpp/compiler-com-support.md)