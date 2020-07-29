---
title: コンパイラの COM サポート
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
ms.openlocfilehash: 9a5961049cbc54c94cec5b444e2d98f013dda932
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233783"
---
# <a name="compiler-com-support"></a>コンパイラの COM サポート

**Microsoft 固有の仕様**

Microsoft C++ コンパイラは、コンポーネントオブジェクトモデル (COM) タイプライブラリを直接読み取り、その内容をコンパイルに含めることができる C++ ソースコードに変換できます。 言語拡張機能を使用して、デスクトップアプリのクライアント側で COM プログラミングを容易にすることができます。

[#Import プリプロセッサディレクティブ](../preprocessor/hash-import-directive-cpp.md)を使用すると、コンパイラは、タイプライブラリを読み取り、COM インターフェイスをクラスとして記述する C++ ヘッダーファイルに変換できます。 一連の `#import` 属性は、結果の種類のライブラリのヘッダー ファイルのコンテンツのユーザー コントロールで使用できます。

[__Declspec](../cpp/declspec.md)拡張属性[uuid](../cpp/uuid-cpp.md)を使用して、COM オブジェクトにグローバル一意識別子 (GUID) を割り当てることができます。 キーワード[__uuidof](../cpp/uuidof-operator.md)は、COM オブジェクトに関連付けられている GUID を抽出するために使用できます。 もう1つの **`__declspec`** 属性である[プロパティ](../cpp/property-cpp.md)は、 `get` `set` COM オブジェクトのデータメンバーに対してメソッドとメソッドを指定するために使用できます。

および型をサポートし `VARIANT` `BSTR` 、スマートポインターを実装し、によってスローされたエラーオブジェクトをカプセル化するために、一連の COM サポートグローバル関数とクラスが用意されてい `_com_raise_error` ます。

- [コンパイラ COM グローバル関数](../cpp/compiler-com-global-functions.md)

- [_bstr_t](../cpp/bstr-t-class.md)

- [_com_error](../cpp/com-error-class.md)

- [_com_ptr_t](../cpp/com-ptr-t-class.md)

- [_variant_t](../cpp/variant-t-class.md)

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラ COM サポートクラス](../cpp/compiler-com-support-classes.md)<br/>
[コンパイラ COM グローバル関数](../cpp/compiler-com-global-functions.md)
