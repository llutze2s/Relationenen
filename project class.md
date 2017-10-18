

public class Project {
	String[][] strings;
	String eingelesen="";
	public Project(String[][] strings) {
		this.strings=strings;
	}
	
	
	public boolean isWellSorted( String[] sequence ){
		
		if (sequence.length<=1)	//mindestlänge >1
			return false;	
		
		for (int i=0;i<sequence.length;i++){
				eingelesen=eingelesen+sequence[i];
				if(check(sequence[i])==false){	//stelle der sequence
					return false;
				}
				
				int j=i+1;
				if(j<sequence.length && eingelesen.contains(sequence[j])){	//prüfe auf mehrfachangabe in sequence menge
					return false;
				}
		}
		
		return true;
	}
	
	public boolean check(String s){
		for(int i=0;i<strings.length;i++){
			if(strings[i][1]==s){	//ist "durchlaufstell" bei irgend einer regel rechts ? 
				if(eingelesen.contains(strings[i][0])){	//ist "durchlaufstell"(links) irgend wo in eingabestring?
					return true;					
				}
				return false;
			}			
		}
		return true;
	}
}


