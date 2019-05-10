---
title: コンパイラの COM サポート
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
ms.openlocfilehash: e13874bad44610821bed9c588af6bd9124162116
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222213"
---
# <a name="compiler-com-support"></a>コンパイラの COM サポート

## <a name="microsoft-specific"></a>Microsoft 固有の仕様

MicrosoftC++コンパイラ直接を読み取り、コンポーネント オブジェクト モデル (COM) タイプ ライブラリにコンテンツを翻訳C++ソース コードをコンパイルに含めることができます。 言語拡張機能はクライアント側の COM プログラミングを簡単にします。

使用して、 [#import プリプロセッサ ディレクティブ](../preprocessor/hash-import-directive-cpp.md)クラスのインターフェイスとして COM を記述する C++ ヘッダー ファイルに変換や、コンパイラは、タイプ ライブラリを読み取ることができます。 一連の `#import` 属性は、結果の種類のライブラリのヘッダー ファイルのコンテンツのユーザー コントロールで使用できます。

使用することができます、 [_ _declspec](../cpp/declspec.md)拡張属性[uuid](../cpp/uuid-cpp.md)を COM オブジェクトへのグローバル一意識別子 (GUID) を割り当てます。 キーワード[_ _uuidof](../cpp/uuidof-operator.md) COM オブジェクトに関連付けられた GUID を抽出するために使用できます。 もう 1 つ **_ _declspec**属性、[プロパティ](../cpp/property-cpp.md)を指定するために使用できる、`get`と`set`COM オブジェクトのデータ メンバーのメソッド。

サポートする一連の COM サポート グローバル関数とクラスが提供される、`VARIANT`と`BSTR`型、スマート ポインターを実装およびによってスローされたエラー オブジェクトをカプセル化`_com_raise_error`:

- [コンパイラ COM のグローバル関数](../cpp/compiler-com-global-functions.md)

- [_bstr_t](../cpp/bstr-t-class.md)

- [_com_error](../cpp/com-error-class.md)

- [_com_ptr_t](../cpp/com-ptr-t-class.md)

- [_variant_t](../cpp/variant-t-class.md)

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)<br/>
[コンパイラ COM のグローバル関数](../cpp/compiler-com-global-functions.md)