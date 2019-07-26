---
title: codecvt_base クラス
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt_base
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
ms.openlocfilehash: 1a32ba5e583fdb20118a3397f1ddb326302f2de1
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459389"
---
# <a name="codecvtbase-class"></a>codecvt_base クラス

と`result`呼ばれる列挙型を定義するために使用される codecvt クラスの基本クラスです。これは、変換の結果を示すためにファセットメンバー関数の戻り値の型として使用されます。

## <a name="syntax"></a>構文

```cpp
class codecvt_base : public locale::facet {
public:
    enum result {ok, partial, error, noconv};
    codecvt_base( size_t _Refs = 0);
    bool always_noconv() const;
    int max_length() const;
    int encoding() const;
    ~codecvt_base()

protected:
    virtual bool do_always_noconv() const;
    virtual int do_max_length() const;
    virtual int do_encoding() const;
};
```

## <a name="remarks"></a>Remarks

このクラスは、テンプレート クラス [codecvt](../standard-library/codecvt-class.md) のすべての特殊化に共通する列挙型を表します。 列挙の結果には、次のような [do_in](../standard-library/codecvt-class.md#do_in) または [do_out](../standard-library/codecvt-class.md#do_out) からの可能な戻り値が示されます。

- `ok`内部と外部の文字エンコーディングの変換が成功した場合。

- `partial`変換先が、変換を成功させるのに十分な大きさでない場合は。

- `error`ソースシーケンスの形式が正しくない場合は。

- 関数で変換が行われない場合は、`noconv`。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
