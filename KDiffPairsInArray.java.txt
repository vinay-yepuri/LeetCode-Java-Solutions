class Solution {
    public int findPairs(int[] nums, int k) {
        
         int result = 0;
	        
	        if ( nums == null || nums.length == 0)
	            return result;
        
            if( k < 0)
                return result;
	        
            HashMap<Integer, Integer> map = new HashMap<>();
        
        for(int num : nums){
                map.put(num, map.getOrDefault(num,0)+1);
        }
        
        for( int key : map.keySet()){
            
            if( k == 0){
                if(map.get(key) > 1) result++;
            }
            else if(map.containsKey(key+k)) result++;
        }
        return result;
    }
}