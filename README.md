project 1 Half Adder
     verilog code
module half_adder (
    input wire A,     // First input bit
    input wire B,     // Second input bit
    output wire SUM,  // Sum output
    output wire CARRY // Carry output
);

// Logic for sum and carry
assign SUM = A ^ B;      // XOR operation for SUM
assign CARRY = A & B;    // AND operation for CARRY
endmodule
    TEST BENCH
module ha_tb_v;

	// Inputs
	reg A;
	reg B;

	// Outputs
	wire SUM;
	wire CARRY;

	// Instantiate the Unit Under Test (UUT)
	half_adder uut (
		.A(A), 
		.B(B), 
		.SUM(SUM), 
		.CARRY(CARRY)
	);

	initial
	     begin
		// Initialize Inputs
		A = 0 ;	B = 0;#10;
		A = 0 ;  B = 1;#10;
		A = 1 ;  B = 0;#10;
		A = 1;   B = 1;#10;
      $finish;
    end
endmodule
