---
title: プロバイダーへのインターフェイスの追加 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB provider templates, object interfaces
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f50459550c91f07c12f6f18b3fbbaa5622ab7408
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032394"
---
# <a name="adding-an-interface-to-your-provider"></a>プロバイダーへのインターフェイスの追加

(通常はデータ ソース、行セット、コマンド、またはセッション オブジェクトに OLE DB プロバイダー ウィザードで作成された) インターフェイスを追加するオブジェクトを決定します。 インターフェイスを追加する必要があるオブジェクトが、プロバイダーが現在サポートされていない 1 つであることができます。 その場合は、ATL OLE DB プロバイダー ウィザード、オブジェクトを作成するを実行します。 クラス ビューでプロジェクトを右クリックし、をクリックして**クラスの追加**から、**追加** メニューをクリック**ATL OLE DB Provider**します。 インターフェイスのコードの別のディレクトリを配置し、プロバイダーのプロジェクトに、ファイルをコピーする場合があります。  
  
インターフェイスをサポートする新しいクラスを作成する場合は、そのクラスから継承するオブジェクトをください。 たとえば、クラスを追加する場合があります**IRowsetIndexImpl**行セット オブジェクトに。  
  
```cpp  
template <class Creator>  
class CAgentRowset :   
    public CRowsetImpl< CAgentRowset<Creator>, CAgentMan, Creator>,  
    public IRowsetIndexImpl< ... >   
```  
  
インターフェイスを追加**COM_MAP** COM_INTERFACE_ENTRY マクロを使用してオブジェクトにします。 マップがない場合は、1 つを作成します。 例えば:  
  
```cpp  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
END_COM_MAP()  
```  
  
行セット オブジェクトのチェーン、親のマップ オブジェクトのオブジェクトが親クラスに委任できるようにします。 この例では、マップに COM_INTERFACE_ENTRY_CHAIN マクロを追加します。  
  
```cpp  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)  
END_COM_MAP()  
```  
  
## <a name="see-also"></a>関連項目  

[OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)