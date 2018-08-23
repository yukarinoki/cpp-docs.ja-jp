---
title: 演算子::interop::typename |Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: a65a105e-7e3a-452f-932f-2cdaf00fbba5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0cf5041e6e3faa8c495d52c31d86ff25c903a174
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600721"
---
# <a name="operator-windowsuixamlinteroptypename"></a>Windows::UI::Xaml::Interop::TypeName 演算子
`Platform::Type` から [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx)変換できるようになります。  
  
## <a name="syntax"></a>構文  
  
```cpp  
Operator TypeName(Platform::Type^ type)  
```  
  
### <a name="return-value"></a>戻り値  
 [が指定されていると、](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) Windows::UI::Xaml::Interop::TypeName `Platform::Type^`が返されます。  
  
### <a name="remarks"></a>Remarks  
 `TypeName` は、型情報を表すための、言語に依存しない Windows ランタイムの構造体です。 [Platform::Type](../cppcx/platform-type-class.md) は C++ に固有で、アプリケーション バイナリ インターフェイス (ABI: Application Binary Interface) を通じて渡すことはできません。 `TypeName`Navigate [関数での](http://msdn.microsoft.com/library/windows/apps/hh702394.aspx) の使用例を次に示します。  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
### <a name="example"></a>例  
 次に、 `TypeName` と `Type`の間の変換方法を示します。  
  
```  
  
// Convert from Type to TypeName  
Windows::UI::Xaml::Interop::TypeName tn = TypeName(MainPage::typeid);  
  
// Convert back from TypeName to Type  
Type^ tx2 = (Type^)(tn);  
  
```  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 .NET framework プログラム プロジェクト`TypeName`として[System.Type](assetId:///System.Type?qualifyHint=False&autoUpgrade=True)します。  
  
### <a name="requirements"></a>要件  
  
## <a name="see-also"></a>関連項目  
 [:interop::typename 演算子](../cppcx/operator-windows-ui-xaml-interop-typename.md)   
 [Platform::Type クラス](../cppcx/platform-type-class.md)