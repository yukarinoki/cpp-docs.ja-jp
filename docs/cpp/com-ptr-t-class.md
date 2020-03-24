---
title: _com_ptr_t クラス
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t
helpviewer_keywords:
- _com_ptr_t class
ms.assetid: 3753a8a0-03d4-4cfd-8a9a-74872ea53971
ms.openlocfilehash: eeaab22ded537cbbb211a79596b8383251af3ab7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189906"
---
# <a name="_com_ptr_t-class"></a>_com_ptr_t クラス

**Microsoft 固有の仕様**

**_Com_ptr_t**オブジェクトは、com インターフェイスポインターをカプセル化し、"スマート" ポインターと呼ばれます。 このテンプレートクラスは、`IUnknown` メンバー関数の関数呼び出し (`QueryInterface`、`AddRef`、および `Release`を通じて、リソースの割り当てと割り当て解除を管理します。

スマート ポインターは通常、_COM_SMARTPTR_TYPEDEF マクロによって提供される typedef 定義で参照されます。 このマクロは、インターフェイス名と IID を受け取り、インターフェイスの名前と `Ptr`のサフィックスを持つ **_com_ptr_t**の特殊化を宣言します。 次に例を示します。

```cpp
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));
```

**_com_ptr_t**特殊化 `IMyInterfacePtr`を宣言します。

このテンプレートクラスのメンバーではなく、一連の[関数テンプレート](../cpp/relational-function-templates.md)は、比較演算子の右側にあるスマートポインターとの比較をサポートしています。

### <a name="construction"></a>構築

|||
|-|-|
|[_com_ptr_t](../cpp/com-ptr-t-com-ptr-t.md)|**_Com_ptr_t**オブジェクトを構築します。|

### <a name="low-level-operations"></a>低水準操作

|||
|-|-|
|[AddRef](../cpp/com-ptr-t-addref.md)|カプセル化されたインターフェイスポインターで `IUnknown` の `AddRef` メンバー関数を呼び出します。|
|[[アタッチ]](../cpp/com-ptr-t-attach.md)|このスマート ポインターの型の生のインターフェイス ポインターをカプセル化します。|
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|`CLSID` または `ProgID`を指定して、オブジェクトの新しいインスタンスを作成します。|
|[[デタッチ]](../cpp/com-ptr-t-detach.md)|カプセル化されたインターフェイス ポインターを抽出して返します。|
|[GetActiveObject](../cpp/com-ptr-t-getactiveobject.md)|`CLSID` または `ProgID`を指定して、オブジェクトの既存のインスタンスにアタッチします。|
|[GetInterfacePtr](../cpp/com-ptr-t-getinterfaceptr.md)|カプセル化されたインターフェイス ポインターを返します。|
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|カプセル化されたインターフェイスポインターで `IUnknown` の `QueryInterface` メンバー関数を呼び出します。|
|[リリース](../cpp/com-ptr-t-release.md)|カプセル化されたインターフェイスポインターで `IUnknown` の `Release` メンバー関数を呼び出します。|

### <a name="operators"></a>オペレーター

|||
|-|-|
|[operator =](../cpp/com-ptr-t-operator-equal.md)|既存の **_com_ptr_t**オブジェクトに新しい値を割り当てます。|
|[演算子 = =、! =、\<、>、\<=、> =](../cpp/com-ptr-t-relational-operators.md)|スマート ポインター オブジェクトを、別のスマート ポインター、生のインターフェイス ポインター、または NULL と比較します。|
|[器](../cpp/com-ptr-t-extractors.md)|カプセル化された COM インターフェイス ポインターを抽出します。|

**Microsoft 固有の仕様はここまで**

## <a name="requirements"></a>必要条件

**ヘッダー:** \<comip .h >

**Lib:** comsuppw または comsuppw (詳細について[は、「/zc: Wchar_t (wchar_t ネイティブ型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 」を参照してください)

## <a name="see-also"></a>参照

[コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)
