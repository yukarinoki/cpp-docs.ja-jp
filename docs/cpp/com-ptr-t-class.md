---
title: _com_ptr_t クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t
dev_langs:
- C++
helpviewer_keywords:
- _com_ptr_t class
ms.assetid: 3753a8a0-03d4-4cfd-8a9a-74872ea53971
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ec54735fce39cc54bdb5e396da7c637b889b92c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="comptrt-class"></a>_com_ptr_t クラス
**Microsoft 固有の仕様**  
  
 `_com_ptr_t` オブジェクトは COM インターフェイス ポインターをカプセル化し、"スマート" ポインターと呼ばれます。 このテンプレート クラスは、リソースの割り当てと関数の呼び出しによる割り当て解除を管理する、 **IUnknown**メンバー関数: `QueryInterface`、 `AddRef`、および**リリース**です。  
  
 スマート ポインターは通常によって提供される typedef 定義で参照されている、 **_COM_SMARTPTR_TYPEDEF**マクロです。 このマクロは、インターフェイス名と IID を受け取り、インターフェイスの名前と `_com_ptr_t` のサフィックスを指定して、`Ptr` の特殊化を宣言します。 例えば:  
  
```  
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
```  
  
 宣言、`_com_ptr_t`特殊化**IMyInterfacePtr**です。  
  
 一連の[関数テンプレート](../cpp/relational-function-templates.md)、このテンプレートのメンバー以外のクラス、比較演算子の右側にあるスマート ポインターを使用して比較をサポートします。  
  
### <a name="construction"></a>構築  
  
|||  
|-|-|  
|[_com_ptr_t](../cpp/com-ptr-t-com-ptr-t.md)|`_com_ptr_t` オブジェクトを構築します。|  
  
### <a name="low-level-operations"></a>低水準操作  
  
|||  
|-|-|  
|[AddRef](../cpp/com-ptr-t-addref.md)|呼び出し、`AddRef`のメンバー関数**IUnknown**カプセル化されたインターフェイス ポインター。|  
|[添付](../cpp/com-ptr-t-attach.md)|このスマート ポインターの型の生のインターフェイス ポインターをカプセル化します。|  
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|指定されたオブジェクトの新しいインスタンスを作成、 **CLSID**または**ProgID**です。|  
|[デタッチ](../cpp/com-ptr-t-detach.md)|カプセル化されたインターフェイス ポインターを抽出して返します。|  
|[GetActiveObject](../cpp/com-ptr-t-getactiveobject.md)|指定されたオブジェクトの既存のインスタンスにアタッチ、 **CLSID**または**ProgID**です。|  
|[GetInterfacePtr](../cpp/com-ptr-t-getinterfaceptr.md)|カプセル化されたインターフェイス ポインターを返します。|  
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|呼び出し、`QueryInterface`のメンバー関数**IUnknown**カプセル化されたインターフェイス ポインター。|  
|[Release](../cpp/com-ptr-t-release.md)|呼び出し、**リリース**のメンバー関数**IUnknown**カプセル化されたインターフェイス ポインター。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 =](../cpp/com-ptr-t-operator-equal.md)|既存の `_com_ptr_t` オブジェクトに新しい値を代入します。|  
|[演算子 = =、! =、 \<、>、 \<=、> =](../cpp/com-ptr-t-relational-operators.md)|スマート ポインター オブジェクトを別のスマート ポインター、生のインターフェイス ポインターの比較または**NULL**です。|  
|[抽出](../cpp/com-ptr-t-extractors.md)|カプセル化された COM インターフェイス ポインターを抽出します。|  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<comip.h >  
  
 **Lib:** comsuppw.lib または comsuppwd.lib (を参照してください[/Zc:wchar_t (wchar_t をネイティブ型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)詳細)  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)