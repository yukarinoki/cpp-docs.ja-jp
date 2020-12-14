---
description: '詳細情報: type_info クラス'
title: type_info Class
ms.date: 11/04/2016
f1_keywords:
- type_info
helpviewer_keywords:
- class type_info
- type_info class
ms.assetid: 894ddda2-7de4-4da3-9404-d2c74e356c16
ms.openlocfilehash: 6be4d6774842ad015b34e771455026ca27e6539b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295316"
---
# <a name="type_info-class"></a>type_info Class

**Type_info** クラスは、コンパイラによってプログラム内で生成される型情報を記述します。 このクラスのオブジェクトは、実質的には型の名前へのポインターを格納します。 **Type_info** クラスには、2つの型の等価性または照合順序の比較に適したエンコード済みの値も格納されます。 型のエンコーディング規則と照合順序については指定されていないため、プログラムによって異なる場合があります。

`<typeinfo>` **Type_info** クラスを使用するには、ヘッダーファイルが含まれている必要があります。 **Type_info** クラスのインターフェイスは次のとおりです。

```cpp
class type_info {
public:
    type_info(const type_info& rhs) = delete; // cannot be copied
    virtual ~type_info();
    size_t hash_code() const;
    _CRTIMP_PURE bool operator==(const type_info& rhs) const;
    type_info& operator=(const type_info& rhs) = delete; // cannot be copied
    _CRTIMP_PURE bool operator!=(const type_info& rhs) const;
    _CRTIMP_PURE int before(const type_info& rhs) const;
    size_t hash_code() const noexcept;
    _CRTIMP_PURE const char* name() const;
    _CRTIMP_PURE const char* raw_name() const;
};
```

クラスにはプライベートコピーコンストラクターしかないため、 **type_info** クラスのオブジェクトを直接インスタンス化することはできません。 (一時) **type_info** オブジェクトを構築する唯一の方法は、 [typeid](../cpp/typeid-operator.md) 演算子を使用することです。 代入演算子もプライベートであるため、 **type_info** クラスのオブジェクトをコピーしたり割り当てたりすることはできません。

`type_info::hash_code`**typeinfo** 型の値をインデックス値の分布にマッピングするために適したハッシュ関数を定義します。

演算子 `==` とを使用すると、 `!=` 他の **type_info** オブジェクトと等しいかどうかを比較できます。

型の照合順序と継承関係には関連性はありません。 `type_info::before`型の照合順序を決定するには、メンバー関数を使用します。 `type_info::before`異なるプログラムまたは同じプログラムの異なる実行で同じ結果が得られる保証はありません。 この方法で `type_info::before` は、はアドレス演算子に似てい `(&)` ます。

この `type_info::name` メンバー関数は、 `const char*` 型の人間が判読できる名前を表す、null で終わる文字列にを返します。 ポイントされたメモリはキャッシュされ、直接解放されることはありません。

この `type_info::raw_name` メンバー関数は、 `const char*` オブジェクト型の装飾名を表す null で終わる文字列にを返します。 実際、名前は保存領域を節約するために、修飾された形式で格納されます。 そのため、この関数は、 `type_info::name` 名前を修飾する必要がないため、より高速です。 関数によって返される文字列は `type_info::raw_name` 比較演算では役立ちますが、読み取ることはできません。 人間が判読できる文字列が必要な場合は、 `type_info::name` 代わりに関数を使用します。

型情報は、 [/gr (Run-Time 型情報の有効化)](../build/reference/gr-enable-run-time-type-information.md) コンパイラオプションが指定されている場合にのみ、ポリモーフィッククラスに対して生成されます。

## <a name="see-also"></a>関連項目

[ランタイム型情報](../cpp/run-time-type-information.md)
