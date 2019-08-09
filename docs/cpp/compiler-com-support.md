---
title: コンパイラの COM サポート
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
ms.openlocfilehash: 421930088dcbf9762d50b5af37d994b9008890eb
ms.sourcegitcommit: 720b74dddb1cdf4e570d55103158304ee1df81f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2019
ms.locfileid: "68606381"
---
# <a name="compiler-com-support"></a>コンパイラの COM サポート

## <a name="microsoft-specific"></a>Microsoft 固有の仕様

Microsoft C++コンパイラは、コンポーネントオブジェクトモデル (COM) タイプライブラリを直接読み取り、その内容をC++コンパイルに含めることができるソースコードに変換できます。 言語拡張機能を使用して、デスクトップアプリのクライアント側で COM プログラミングを容易にすることができます。

[#Import プリプロセッサディレクティブ](../preprocessor/hash-import-directive-cpp.md)を使用すると、コンパイラは、タイプライブラリを読み取り、COM インターフェイスC++をクラスとして記述するヘッダーファイルに変換できます。 一連の `#import` 属性は、結果の種類のライブラリのヘッダー ファイルのコンテンツのユーザー コントロールで使用できます。

[__Declspec](../cpp/declspec.md)拡張属性[uuid](../cpp/uuid-cpp.md)を使用して、グローバル一意識別子 (GUID) を COM オブジェクトに割り当てることができます。 キーワード[__uuidof](../cpp/uuidof-operator.md)は、COM オブジェクトに関連付けられている GUID を抽出するために使用できます。 別の **__declspec**属性である[プロパティ](../cpp/property-cpp.md)を使用して、 `get` COM `set`オブジェクトのデータメンバーに対してメソッドおよびメソッドを指定できます。

`VARIANT`および`_com_raise_error`型をサポートし、スマートポインターを実装し、によってスローされたエラーオブジェクトをカプセル化するために、一連の COM サポートグローバル関数とクラスが用意されています。 `BSTR`

- [コンパイラ COM のグローバル関数](../cpp/compiler-com-global-functions.md)

- [_bstr_t](../cpp/bstr-t-class.md)

- [_com_error](../cpp/com-error-class.md)

- [_com_ptr_t](../cpp/com-ptr-t-class.md)

- [_variant_t](../cpp/variant-t-class.md)

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)<br/>
[コンパイラ COM のグローバル関数](../cpp/compiler-com-global-functions.md)
