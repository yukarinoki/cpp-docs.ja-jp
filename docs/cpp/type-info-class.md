---
title: type_info Class
ms.date: 11/04/2016
f1_keywords:
- type_info
helpviewer_keywords:
- class type_info
- type_info class
ms.assetid: 894ddda2-7de4-4da3-9404-d2c74e356c16
ms.openlocfilehash: 7a016fe8fee4e5765e6172184bfa9c90eecbc687
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160672"
---
# <a name="type_info-class"></a>type_info Class

**Type_info**クラスは、コンパイラによってプログラム内で生成される型情報を記述します。 このクラスのオブジェクトは、実質的には型の名前へのポインターを格納します。 **Type_info**クラスには、2つの型の等価性または照合順序の比較に適したエンコード済みの値も格納されます。 型のエンコーディング規則と照合順序については指定されていないため、プログラムによって異なる場合があります。

**Type_info**クラスを使用するには、`<typeinfo>` ヘッダーファイルが含まれている必要があります。 **Type_info**クラスのインターフェイスは次のとおりです。

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

クラスにはプライベートコピーコンストラクターしかないため、 **type_info**クラスのオブジェクトを直接インスタンス化することはできません。 (一時) **type_info**オブジェクトを構築する唯一の方法は、 [typeid](../cpp/typeid-operator.md)演算子を使用することです。 代入演算子もプライベートであるため、 **type_info**クラスのオブジェクトをコピーしたり割り当てたりすることはできません。

`type_info::hash_code` は、 **typeinfo**型の値をインデックス値の分布にマッピングするために適したハッシュ関数を定義します。

演算子 `==` と `!=` を使用すると、他の**type_info**オブジェクトと等しいかどうかを比較できます。

型の照合順序と継承関係には関連性はありません。 型の照合順序を決定するには、`type_info::before` メンバー関数を使用します。 `type_info::before` によって、プログラムが異なる場合や、同じプログラムの実行が異なる場合でも、同じ結果が得られるという保証はありません。 このように、`type_info::before` は `(&)` オペレーターのアドレスと似ています。

`type_info::name` メンバー関数は、型の人間が判読できる名前を表す null で終わる文字列に `const char*` を返します。 ポイントされたメモリはキャッシュされ、直接解放されることはありません。

`type_info::raw_name` メンバー関数は、オブジェクト型の装飾名を表す null で終わる文字列に `const char*` を返します。 実際、名前は保存領域を節約するために、修飾された形式で格納されます。 したがって、この関数は、名前を修飾する必要がないため、`type_info::name` よりも高速です。 `type_info::raw_name` 関数によって返される文字列は、比較操作では役立ちますが、読み取ることはできません。 人間が判読できる文字列が必要な場合は、代わりに `type_info::name` 関数を使用します。

型情報は、 [/gr (実行時の型情報の有効化)](../build/reference/gr-enable-run-time-type-information.md)コンパイラオプションが指定されている場合にのみ、ポリモーフィックなクラスに対して生成されます。

## <a name="see-also"></a>参照

[ランタイム型情報](../cpp/run-time-type-information.md)
