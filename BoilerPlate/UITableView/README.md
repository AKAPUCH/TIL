<details><summary><h2>2줄짜리 텍스트 넣기</h2></summary>

생성 시 style을 subtitle로 지정하면 된다. 기본 셀을 사용한다면 ios 14.0 이하는 textLabel과 detailTextLabel을, 이후는 defaultContentConfiguration을 통해 텍스트 설정이 가능하다
```swift

import UIKit
class MenuCell: UITableViewCell {
    
    static let identifier = "reused"

    override init(style: UITableViewCell.CellStyle, reuseIdentifier: String?) {
        super.init(style: .subtitle, reuseIdentifier: reuseIdentifier)
        setDefaultProperty()
    }
    
    required init?(coder: NSCoder) {
        fatalError("init(coder:) has not been implemented")
    }
    
    func setDefaultProperty() { 
        backgroundColor = .white
  
         // ios 14.0 이후 deprecated된 textLabel, detailTextLabel 등 대응
        var content = self.defaultContentConfiguration()
        content.textProperties.font 
        content.textProperties.color
        
        content.secondaryTextProperties.font
        content.secondaryTextProperties.color
        
        self.contentConfiguration = content
    }
    
}
  
```
	
</details>
