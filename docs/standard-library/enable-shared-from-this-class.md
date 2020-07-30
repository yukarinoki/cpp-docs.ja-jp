---
title: enable_shared_from_this クラス
ms.date: 11/04/2016
f1_keywords:
- memory/std::enable_shared_from_this
helpviewer_keywords:
- enable_shared_from_this class
- enable_shared_from_this
ms.assetid: 9237603d-22e2-421f-b070-838ac006baf5
ms.openlocfilehash: 9b417eabdaf6002724a0fa947dd97dea6f0df0a5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217780"
---
# <a name="enable_shared_from_this-class"></a>enable_shared_from_this クラス

`shared_ptr` の生成を支援します。

## <a name="syntax"></a>構文

```cpp
class enable_shared_from_this {
public:
    shared_ptr<Ty>
        shared_from_this();
    shared_ptr<const Ty> shared_from_this() const;
    weak_ptr<T> weak_from_this() noexcept;
    weak_ptr<T const> weak_from_this() const noexcept;
protected:
    enable_shared_from_this();
    enable_shared_from_this(const enable_shared_from_this&);
    enable_shared_from_this& operator=(const enable_shared_from_this&);
    ~enable_shared_from_this();
};
```

### <a name="parameters"></a>パラメーター

*~*\
共有ポインターによって制御される型。

## <a name="remarks"></a>解説

`enable_shared_from_this` の派生オブジェクトは、メンバー関数の `shared_from_this` メソッドを使って、既存の `shared_ptr` 所有者と所有権を共有するインスタンスの [shared_ptr](../standard-library/shared-ptr-class.md) 所有者を作成できます。 それ以外の場合、を使用して新しいを作成した場合は、 `shared_ptr` **`this`** 既存の所有者とは区別されます。これにより、 `shared_ptr` 無効な参照が発生したり、オブジェクトが複数回削除されたりする可能性があります。

コンストラクター、デストラクター、および代入演算子は、偶発的な誤用を防ぐために保護されています。 テンプレート引数の型*Ty*は、派生クラスの型である必要があります。

使用方法の例については、「[enable_shared_from_this::shared_from_this](#shared_from_this)」をご覧ください。

## <a name="shared_from_this"></a><a name="shared_from_this"></a>shared_from_this

インスタンスの所有権を既存の `shared_ptr` 所有者と共有する `shared_ptr` を生成します。

```cpp
shared_ptr<T> shared_from_this();
shared_ptr<const T> shared_from_this() const;
```

### <a name="remarks"></a>解説

基底クラス `enable_shared_from_this` からオブジェクトを派生すると、`shared_from_this` テンプレート メンバー関数は、このインスタンスの所有権を既存の `shared_ptr` 所有者と共有する [shared_ptr クラス](../standard-library/shared-ptr-class.md)のオブジェクトを返します。 それ以外の場合、から新しいを作成した場合は、 `shared_ptr` **`this`** 既存の所有者とは別になり `shared_ptr` ます。これにより、無効な参照が発生したり、オブジェクトが複数回削除されたりする可能性があります。 `shared_ptr` オブジェクトによってまだ所有されていないインスタンスで `shared_from_this` を呼び出した場合の動作は未定義です。

### <a name="example"></a>例

```cpp
// std_memory_shared_from_this.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

struct base : public std::enable_shared_from_this<base>
{
    int val;
    shared_ptr<base> share_more()
    {
        return shared_from_this();
    }
};

int main()
{
    auto sp1 = make_shared<base>();
    auto sp2 = sp1->share_more();

    sp1->val = 3;
    cout << "sp2->val == " << sp2->val << endl;
    return 0;
}
```

```Output
sp2->val == 3
```

## <a name="weak_from_this"></a><a name="weak_from_this"></a>weak_from_this

```cpp
weak_ptr<T> weak_from_this() noexcept;
weak_ptr<T const> weak_from_this() const noexcept;
```
