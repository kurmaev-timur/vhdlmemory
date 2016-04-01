# vhdlmemory
Элемент памяти описанный на языке VHDL 
library ieee; 
use ieee.std_logic_1164.all;

entity mem is
port (
     clock    : in  std_logic;
     address  : in  std_logic_vector (7 downto 0);
     data_out : out std_logic_vector (5 downto 0));
end mem;

architecture rtl of mem is
begin
process (clock)
begin
	if rising_edge (clock) then
		case address is
			when "00000000" => data_out <= "000111";
			when "00000001" => data_out <= "000110";
			when "00000010" => data_out <= "000010";
			when "00000011" => data_out <= "100000";
			when "00000100" => data_out <= "100010";
			when "00000101" => data_out <= "001110";
			when "00000110" => data_out <= "111100";
			when "00000111" => data_out <= "110111";
			when "00001000" => data_out <= "111000";
			when "00001001" => data_out <= "100110";
			when others => data_out <= "101111";
		end case;
	end if;
end process;
end rtl;
