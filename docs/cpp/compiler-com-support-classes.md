---
title: コンパイラ COM サポート クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_raise_error
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3403a09700ba6f84792cc570d9fb093026241d8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070824"
---
# <a name="compiler-com-support-classes"></a>コンパイラ COM サポート クラス

**Microsoft 固有の仕様**

標準クラスは、COM 型の一部をサポートするために使用されます。 クラスが定義されている\<comdef.h > とタイプ ライブラリから生成されたヘッダー ファイル。

|クラス|目的|
|-----------|-------------|
|[_bstr_t](../cpp/bstr-t-class.md)|便利な演算子とメソッドを提供するために、`BSTR` 型をラップします。|
|[_com_error](../cpp/com-error-class.md)|によってスローされたエラー オブジェクトを定義します[_com_raise_error](../cpp/com-raise-error.md)ほとんどエラーが発生します。|
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|COM インターフェイス ポインターをカプセル化し、必要な呼び出しを自動化`AddRef`、 `Release`、および`QueryInterface`します。|
|[_variant_t](../cpp/variant-t-class.md)|便利な演算子とメソッドを提供するために、`VARIANT` 型をラップします。|

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラ COM サポート](../cpp/compiler-com-support.md)<br/>
[コンパイラ COM のグローバル関数](../cpp/compiler-com-global-functions.md)<br/>
[C++ 言語リファレンス](../cpp/cpp-language-reference.md)