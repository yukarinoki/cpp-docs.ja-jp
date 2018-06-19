---
title: type_info クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- type_info
dev_langs:
- C++
helpviewer_keywords:
- class type_info
- type_info class
ms.assetid: 894ddda2-7de4-4da3-9404-d2c74e356c16
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3e3138c9028f72327c9d4bf2c2f2e82c942dbde
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32422437"
---
# <a name="typeinfo-class"></a>type_info Class
**Type_info**クラスは、コンパイラによって、プログラム内で生成される型情報を表します。 このクラスのオブジェクトは、実質的には型の名前へのポインターを格納します。 **Type_info**クラスもまたは照合順序の 2 つの型の等価性を比較するのに適したエンコードした値を格納します。 型のエンコーディング規則と照合順序については指定されていないため、プログラムによって異なる場合があります。  
  
 `<typeinfo>`ヘッダー ファイルを使用するために含める必要があります、 **type_info**クラスです。 インターフェイス、 **type_info**クラスは。  
  
```cpp
class type_info {  
public:  
    virtual ~type_info();  
    size_t hash_code() const  
    _CRTIMP_PURE bool operator==(const type_info& rhs) const;  
    _CRTIMP_PURE bool operator!=(const type_info& rhs) const;  
    _CRTIMP_PURE int before(const type_info& rhs) const;  
    _CRTIMP_PURE const char* name() const;  
    _CRTIMP_PURE const char* raw_name() const;  
};  
```  
  
 オブジェクトをインスタンス化することはできません、 **type_info**クラスを直接クラスがプライベート コピー コンス トラクターのみを持つためです。 (一時) を構築する唯一の方法**type_info**オブジェクトは、使用する、 [typeid](../cpp/typeid-operator.md)演算子。 代入演算子もプライベートであるため、コピーまたはクラスのオブジェクトを代入することはできません**type_info**です。  
  
 **type_info::hash_code**型の値をマッピングするために適したハッシュ関数を定義**typeinfo**インデックス値の分布にします。  
  
 演算子は、`==`と`!=`を他の等値演算子および非等値の比較に使用できる**type_info**オブジェクトをそれぞれします。  
  
 型の照合順序と継承関係には関連性はありません。 使用して、 **type_info::before**メンバー関数の種類の照合順序を決定します。 保証はありませんを**type_info::before**さまざまなプログラムや、同じプログラムの別の実行で同じ結果を得られます。 この方法で**type_info::before**アドレスのような **(&)** 演算子。  
  
 **Type_info::name**メンバー関数を返します、 **const char\*** 型の人間が判読できる名前を表す null で終わる文字列にします。 ポイントされたメモリはキャッシュされ、直接解放されることはありません。  
  
 **:Raw_name**メンバー関数を返します、 **const char\*** オブジェクトの種類の装飾名を表す null で終わる文字列にします。 実際、名前は保存領域を節約するために、修飾された形式で格納されます。 そのため、この関数はよりも高速**type_info::name**に名前を外す必要がないためです。 によって返される文字列、 **:raw_name**関数は、比較操作で役に立ちますが、読み取ることができません。 人間が判読できる文字列を必要がある場合、 **type_info::name**関数を使用します。  
  
 場合にのみ、ポリモーフィックなクラスの型情報が生成される、 [/GR (ランタイム型情報の有効化)](../build/reference/gr-enable-run-time-type-information.md)コンパイラ オプションを指定します。  
  
## <a name="see-also"></a>関連項目  
 [ランタイム型情報](../cpp/run-time-type-information.md)
