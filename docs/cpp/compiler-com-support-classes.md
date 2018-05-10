---
title: コンパイラ COM サポート クラス |Microsoft ドキュメント
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
ms.openlocfilehash: f4fe4e7c26d1b32f16d524407279e5e71534d00c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="compiler-com-support-classes"></a>コンパイラ COM サポート クラス
**Microsoft 固有の仕様**  
  
 標準クラスは、COM 型の一部をサポートするために使用されます。 クラスが定義されている\<comdef.h > と、タイプ ライブラリから生成されたヘッダー ファイルです。  
  
|クラス|目的|  
|-----------|-------------|  
|[_bstr_t](../cpp/bstr-t-class.md)|便利な演算子とメソッドを提供するために、`BSTR` 型をラップします。|  
|[_com_error](../cpp/com-error-class.md)|によってスローされたエラー オブジェクトを定義[_com_raise_error](../cpp/com-raise-error.md)でほとんどの障害が発生します。|  
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|COM インターフェイス ポインターをカプセル化し、必要な呼び出しを自動化`AddRef`、**リリース**、および`QueryInterface`です。|  
|[_variant_t](../cpp/variant-t-class.md)|ラップ、**バリアント**便利な演算子とメソッドを提供する型。|  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ COM サポート](../cpp/compiler-com-support.md)   
 [コンパイラ COM グローバル関数](../cpp/compiler-com-global-functions.md)   
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)