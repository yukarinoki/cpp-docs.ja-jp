---
title: スレッド処理 (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.threading
dev_langs:
- C++
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f21ea8c16b4e09a5ad1845a10797be00f91b0d8f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="threading-c"></a>threading (C++)
COM オブジェクトのスレッド モデルを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ threading(  
   model=enumeration  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 ***モデル***(省略可能)  
 次のスレッド モデルのいずれか。  
  
-   **アパートメント**(アパートメント スレッド)  
  
-   **ニュートラル**(.NET Framework コンポーネントをユーザー インターフェイスなしの)  
  
-   **1 つ**(単純なスレッド)  
  
-   **空き**(スレッドを解放)。  
  
-   **両方**(アパートメントおよびフリー スレッドの)  
  
 既定値は**アパートメント**です。  
  
## <a name="remarks"></a>コメント  
 **スレッド**C++ 属性が生成された .idl ファイルに表示されないが、COM オブジェクトの実装で使用されます。  
  
 ATL プロジェクトの場合、[コクラス](../windows/coclass.md)attribute が存在するで指定されたスレッド モデル*モデル*をテンプレート パラメーターとして渡されます、 [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md)クラス、によって挿入された、**コクラス**属性。  
  
 **スレッド**属性がへのアクセスを防ぐことも、 [event_source](../windows/event-source.md)です。  
  
## <a name="example"></a>例  
 参照してください、[ライセンス](../windows/licensed.md)のサンプルの使用例**スレッド**です。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**class**、 `struct`|  
|**反復可能**|×|  
|**必要な属性**|**coclass**|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [COM 属性](../windows/com-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
 [古いコード (Visual C) のためのマルチ スレッド処理のサポート](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
 [ニュートラル アパートメント](http://msdn.microsoft.com/library/windows/desktop/ms681813)   
