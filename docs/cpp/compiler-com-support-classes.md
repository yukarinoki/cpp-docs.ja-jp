---
description: 詳細については、「コンパイラ COM サポートクラス」を参照してください。
title: コンパイラ COM サポート クラス
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
ms.openlocfilehash: e2f921e9c3ebe759109d741630afe56f6af30bbc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344706"
---
# <a name="compiler-com-support-classes"></a>コンパイラ COM サポート クラス

**Microsoft 固有の仕様**

標準クラスは、COM 型の一部をサポートするために使用されます。 クラスは、 \<comdef.h> およびタイプライブラリから生成されたヘッダーファイルで定義されています。

|クラス|目的|
|-----------|-------------|
|[_bstr_t](../cpp/bstr-t-class.md)|便利な演算子とメソッドを提供するために、`BSTR` 型をラップします。|
|[_com_error](../cpp/com-error-class.md)|ほとんどのエラーで [_com_raise_error](../cpp/com-raise-error.md) によってスローされるエラーオブジェクトを定義します。|
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|COM インターフェイスポインターをカプセル化し、、、およびへの必要な呼び出しを自動化し `AddRef` `Release` `QueryInterface` ます。|
|[_variant_t](../cpp/variant-t-class.md)|便利な演算子とメソッドを提供するために、`VARIANT` 型をラップします。|

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの COM サポート](../cpp/compiler-com-support.md)<br/>
[コンパイラ COM グローバル関数](../cpp/compiler-com-global-functions.md)<br/>
[C++ 言語リファレンス](../cpp/cpp-language-reference.md)
