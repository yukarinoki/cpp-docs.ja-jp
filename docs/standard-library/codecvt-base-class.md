---
title: codecvt_base クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocale/std::codecvt_base
dev_langs:
- C++
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a471cdd63ed46e15c9ec41968ed341eefaf36963
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965393"
---
# <a name="codecvtbase-class"></a>codecvt_base クラス

列挙型を定義するために使用される codecvt クラスの基本クラスとして参照`result`変換の結果を示すためにファセットのメンバー関数の戻り値の型として使用されます。

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

- `ok` 内部および外部の文字エン コードの間の変換が成功するとします。

- `partial` 場合は、変換先が変換を正常に十分な大きさではありません。

- `error` ソース シーケンスが無効である場合は、次の形式。

- 関数で変換が行われない場合は、`noconv`。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
