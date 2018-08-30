---
title: 型演算子 ^ |Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: b24ffc83-0780-4f9a-8ee0-f5725db339d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8530a3c896d5c1dfa6568e166b9a0a43c0f0b0fc
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208088"
---
# <a name="operator-type"></a>Type^ 演算子
変換を有効[::interop::typename](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx)に`Platform::Type`します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
Operator Type^(Windows::UI::Xaml::Interop::TypeName typeName)  
```  
  
### <a name="return-value"></a>戻り値  
 返します、`Platform::Type`が指定されると、 [::interop::typename](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx)します。  
  
### <a name="remarks"></a>Remarks  
 `TypeName` は、型情報を表すための、言語に依存しない Windows ランタイムの構造体です。 [Platform::Type](../cppcx/platform-type-class.md) は C++ に固有で、アプリケーション バイナリ インターフェイス (ABI: Application Binary Interface) を通じて渡すことはできません。 ここでの用途の 1 つは、`TypeName`の[Navigate](https://msdn.microsoft.com/library/windows/apps/hh702394.aspx)関数。  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
### <a name="example"></a>例  
 次に、 `TypeName` と `Type`の間の変換方法を示します。  
  
```  
  
// Convert from Type to TypeName  
TypeName tn = TypeName(MainPage::typeid);  
  
// Convert back from TypeName to Type  
Type^ tx2 = (Type^)(tn);  
  
```  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 .NET framework プログラム プロジェクト`TypeName`として[System.Type](assetId:///System.Type?qualifyHint=False&autoUpgrade=True)します。  
  
### <a name="requirements"></a>要件  
  
## <a name="see-also"></a>関連項目  
 [:interop::typename 演算子](../cppcx/operator-windows-ui-xaml-interop-typename.md)   
 [Platform::Type クラス](../cppcx/platform-type-class.md)